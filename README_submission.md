# Báo cáo Thực hành Lab 17 - Multi-Memory Agent với Zep

## 1. Trả lời 3 câu hỏi cốt lõi
- **Layer quan trọng nhất:** Long-term Memory là layer quan trọng nhất trong bộ test vì chiếm 4/11 case (E02, E03, E08, E09), quyết định khả năng duy trì sở thích cross-session (Python/NestJS) và theo dõi open-loop task (E03).
- **Trade-off Zep Context Block vs Redis + Qdrant:** Zep cung cấp Graph Memory tự động trích xuất entities/facts, xử lý recency và user context block tích hợp sẵn nhưng có latency cao hơn (~1.1s) và phụ thuộc Cloud. Ngược lại, Redis/Qdrant có tốc độ cực nhanh (<1ms), toàn quyền kiểm soát dữ liệu nhưng đòi hỏi tự xây dựng pipeline trích xuất tri thức, resolve mâu thuẫn và quản lý ngân sách ngữ cảnh.
- **Guardrail chống Memory Poisoning:** Áp dụng (1) Human/Policy review trước khi ghi đè durable facts; (2) Lưu provenance/timestamp để truy vết nguồn gốc thông tin; (3) Cô lập namespace theo `user_id`; (4) Giới hạn token budget (10/4/3/3) để ngăn context injection tràn bộ nhớ.

## 2. Phân tích kết quả Benchmark
- **Layer có hit rate thấp nhất (No-memory):** Long-term, Episodic và Semantic đều 0% trên baseline no-memory (chỉ Short-term đạt 100% nhờ context cục bộ).
- **Case retrieve nhiều token nhất:** E03 (1,374 tokens) và E02 (1,353 tokens) do Context Block nạp tổng hợp User Summary và Fact Edges.
- **Case Mixed (E07):** Kết hợp Long-term (`Python`) và Semantic (`Idempotency-Key`).
- **Token Reduction vs Hit Rate:** No-memory có reduction cao (81.8%) chỉ vì nó không truy xuất được gì, dẫn đến hit rate tệ hại (18.2%). Agent có memory đạt hit rate 100% với token reduction trung bình 14.2% (riêng Semantic giảm tới 74.2%), tối ưu hóa context mà không làm mất chứng cứ.

## 3. Phân tích Recency (E08) và Compaction (E10)
- **Recency (E08):** Zep áp dụng quy tắc *recency wins*, ghi đè và ưu tiên stack mới TypeScript/NestJS cho BLUEBIRD-42 mà không bị nhiễu bởi preference cũ.
- **Compaction (E10):** Khi hội thoại vượt ngưỡng sliding window, compaction nén các turn phụ vào session summary nhưng bảo tồn nguyên vẹn ràng buộc `REVIEW-DEADLINE-1600` trong Durable Notes.
