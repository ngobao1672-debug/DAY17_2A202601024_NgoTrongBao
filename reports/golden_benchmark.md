# Lab 17 Golden Set Report

- Implementation: `student`
- Kind: `golden`
- Cases: **20**
- Passed: **20/20**
- Evidence hit rate: **100.0%**
- Average retrieval latency: **1578.8 ms**
- Average token reduction vs full source context: **5.6%**
- Golden bonus: **10/10** (100% required)

| Case | Layer | Pass | Latency ms | Retrieved tokens | Token reduction | Missing / Error |
| --- | --- | --- | ---: | ---: | ---: | --- |
| G01 | short_term | PASS | 0.4 | 227 | 0.0% |  |
| G02 | short_term | PASS | 0.0 | 133 | 0.0% |  |
| G06 | long_term | PASS | 1947.7 | 807 | 0.0% |  |
| G09 | semantic | PASS | 307.9 | 288 | 37.2% |  |
| G10 | semantic | PASS | 277.1 | 270 | 41.2% |  |
| G14 | mixed | PASS | 2180.6 | 581 | 0.0% |  |
| G03 | long_term | PASS | 2136.9 | 1361 | 0.0% |  |
| G04 | long_term | PASS | 2182.0 | 1382 | 0.0% |  |
| G07 | episodic | PASS | 277.4 | 564 | 0.0% |  |
| G08 | episodic | PASS | 405.6 | 578 | 0.0% |  |
| G11 | mixed | PASS | 2647.3 | 581 | 0.0% |  |
| G13 | mixed | PASS | 608.3 | 500 | 11.5% |  |
| G15 | mixed | PASS | 3717.2 | 831 | 0.0% |  |
| G16 | mixed | PASS | 2400.9 | 581 | 0.0% |  |
| G17 | mixed | PASS | 2787.0 | 581 | 0.0% |  |
| G18 | mixed | PASS | 601.8 | 500 | 11.5% |  |
| G19 | mixed | PASS | 2679.8 | 581 | 0.0% |  |
| G05 | long_term | PASS | 2138.2 | 1352 | 0.0% |  |
| G12 | mixed | PASS | 2142.5 | 560 | 11.4% |  |
| G20 | mixed | PASS | 2137.8 | 756 | 0.0% |  |

## Evidence excerpts

### G01 - short_term

`<SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. | assistant: Noted staging constraint. | user: Filler A about button padding. | assistant: Filler A. | user: Filler B about color tokens. | assistant: Filler B. | user: Filler C about copy tone. | assistant: Filler C. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. - user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. - assistant: Noted staging constraint. </DURA`

### G02 - short_term

`<RECENT_TURNS> user: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. assistant: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. user: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. assistant: Toi se uu tien timeline khi giai thich coroutine va Task. user: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. </RECENT_TURNS>`

### G06 - long_term

`<USER_SUMMARY> Lan's project is LOTUS-88. They prioritize Java and Spring Boot for backend development and do not use Python in this context. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-01 11:00:00     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Lan Tran" }: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien Java va Spring Boot, va khong dung Python trong vi du backend.   - Created At: 2026-08-01 11:00:20     Source: message     Content: Lab Assistant (assistant): Da hieu: LOTUS-88, Java + Spring Boot cho backend examples. </EPI`

### G09 - semantic

`EPISODE: {"id":"kb-payment-retry","entity":"Payment API Retry Policy","summary":"For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3.","source":"internal-api-guideline-v3","updated_at":"2026-08-10T00:00:00Z"} metadata= EPISODE: For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3. metadata= EPISODE: {"id":"kb-context-budget","entity":"Memory Context Budget","summary":"Reserve bounded context for `

### G10 - semantic

`EPISODE: Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL. metadata= EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL.","source":"memory-governance-policy","updated_at":"2026-08-12T00:00:00Z"} metadata= EPISODE: {"id":"kb-context-budget","entity":"Memory Context Budget","summary":"Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodi`

### G14 - mixed

`<LONG_TERM> <USER_SUMMARY> Lan's project is LOTUS-88. They prioritize Java and Spring Boot for backend development and do not use Python in this context. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-01 11:00:00     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Lan Tran" }: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien Java va Spring Boot, va khong dung Python trong vi du backend.   - Created At: 2026-08-01 11:00:20     Source: message     Content: Lab Assistant (assistant): Da hieu: LOTUS-88, Java + Spring Boot cho backend exa`

### G03 - long_term

`<USER_SUMMARY> The user's personal project is named ORCHID-27. For company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project's backend. Python is still preferred for personal demos related to ORCHID-27.  The user likes Python and dislikes Java. They prefer short code examples when explaining code. Their personal project is ORCHID-27. They have a recurring goal to complete a benchmark report for LAB-REPORT-1600 by Saturday at 16:00.  When explaining async/await, coroutines, and Tasks, use a timeline format. The AI will prioritize using a timeline when explaining coroutines and Tasks. </USER_SUMMARY>  <EPISODES> Episodes are source `

### G04 - long_term

`<USER_SUMMARY> The user's personal project is named ORCHID-27. For company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project's backend. Python is still preferred for personal demos related to ORCHID-27.  The user likes Python and dislikes Java. They prefer short code examples when explaining code. Their personal project is ORCHID-27. They have a recurring goal to complete a benchmark report for LAB-REPORT-1600 by Saturday at 16:00.  When explaining async/await, coroutines, and Tasks, use a timeline format. The AI will prioritize using a timeline when explaining coroutines and Tasks. </USER_SUMMARY>  <EPISODES> Episodes are source `

### G07 - episodic

`EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Da ghi nhan trajectory: increase timeout khong hieu qua; ClientSession + concurrency=20 giai quyet connection churn. EPISODE: Voi demo ca nhan cua Minh, ngon ngu uu tien la gi? EPISODE: Minh sap viet `

### G08 - episodic

`EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. EPISODE: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Hay chon huong dan code retry payment phu hop voi preference ca nhan cua Min`

### G11 - mixed

`<LONG_TERM> <USER_SUMMARY> The user's personal project is named ORCHID-27. For company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project's backend. Python is still preferred for personal demos related to ORCHID-27.  The user likes Python and dislikes Java. They prefer short code examples when explaining code. Their personal project is ORCHID-27. They have a recurring goal to complete a benchmark report for LAB-REPORT-1600 by Saturday at 16:00.  When explaining async/await, coroutines, and Tasks, use a timeline format. The AI will prioritize using a timeline when explaining coroutines and Tasks. </USER_SUMMARY>  <EPISODES> Episodes`

### G13 - mixed

`<EPISODIC> EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Da ghi nhan trajectory: increase timeout khong hieu qua; ClientSession + concurrency=20 giai quyet connection churn. EPISODE: Hay chon huong dan code retry payment phu hop voi preference ca nhan cua Minh. EPISODE: Mai hop mentor, toi nay minh muon don open-loop. Liet ke viec chua dong, deadline,`

### G15 - mixed

`<LONG_TERM> <USER_SUMMARY> The user's personal project is named ORCHID-27. For company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project's backend. Python is still preferred for personal demos related to ORCHID-27.  The user likes Python and dislikes Java. They prefer short code examples when explaining code. Their personal project is ORCHID-27. They have a recurring goal to complete a benchmark report for LAB-REPORT-1600 by Saturday at 16:00.  When explaining async/await, coroutines, and Tasks, use a timeline format. The AI will prioritize using a timeline when explaining coroutines and Tasks. </USER_SUMMARY>  <EPISODES> Episodes`

### G16 - mixed

`<LONG_TERM> <USER_SUMMARY> The user's personal project is named ORCHID-27. For company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project's backend. Python is still preferred for personal demos related to ORCHID-27.  The user likes Python and dislikes Java. They prefer short code examples when explaining code. Their personal project is ORCHID-27. They have a recurring goal to complete a benchmark report for LAB-REPORT-1600 by Saturday at 16:00.  When explaining async/await, coroutines, and Tasks, use a timeline format. The AI will prioritize using a timeline when explaining coroutines and Tasks. </USER_SUMMARY>  <EPISODES> Episodes`

### G17 - mixed

`<LONG_TERM> <USER_SUMMARY> The user's personal project is named ORCHID-27. For company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project's backend. Python is still preferred for personal demos related to ORCHID-27.  The user likes Python and dislikes Java. They prefer short code examples when explaining code. Their personal project is ORCHID-27. They have a recurring goal to complete a benchmark report for LAB-REPORT-1600 by Saturday at 16:00.  When explaining async/await, coroutines, and Tasks, use a timeline format. The AI will prioritize using a timeline when explaining coroutines and Tasks. </USER_SUMMARY>  <EPISODES> Episodes`

### G18 - mixed

`<EPISODIC> EPISODE: Minh sap viet script ca nhan de tai hien su co latency, muon code dung ngon ngu minh thich khi lam mot minh, dong thoi bam sat playbook incident cua lab chu dung vo tang timeout. G EPISODE: Minh con mot open-loop phai nop truoc deadline, dong thoi muon ghi chu retry payment dung so lan toi da theo policy. Nac lai ma task/deadline con dang do, va gioi han retry chinh t EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. EPISODE: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-16`

### G19 - mixed

`<LONG_TERM> <USER_SUMMARY> The user's personal project is named ORCHID-27. For company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project's backend. Python is still preferred for personal demos related to ORCHID-27.  The user likes Python and dislikes Java. They prefer short code examples when explaining code. Their personal project is ORCHID-27. They have a recurring goal to complete a benchmark report for LAB-REPORT-1600 by Saturday at 16:00.  When explaining async/await, coroutines, and Tasks, use a timeline format. The AI will prioritize using a timeline when explaining coroutines and Tasks. </USER_SUMMARY>  <EPISODES> Episodes`

### G05 - long_term

`<USER_SUMMARY> The user's personal project is named ORCHID-27. For company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project's backend. Python is still preferred for personal demos related to ORCHID-27.  The user likes Python and dislikes Java. They prefer short code examples when explaining code. Their personal project is ORCHID-27. They have a recurring goal to complete a benchmark report for LAB-REPORT-1600 by Saturday at 16:00.  When explaining async/await, coroutines, and Tasks, use a timeline format. The AI will prioritize using a timeline when explaining coroutines and Tasks. </USER_SUMMARY>  <EPISODES> Episodes are source `

### G12 - mixed

`<LONG_TERM> <USER_SUMMARY> The user's personal project is named ORCHID-27. For company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used for this project's backend. Python is still preferred for personal demos related to ORCHID-27.  The user likes Python and dislikes Java. They prefer short code examples when explaining code. Their personal project is ORCHID-27. They have a recurring goal to complete a benchmark report for LAB-REPORT-1600 by Saturday at 16:00.  When explaining async/await, coroutines, and Tasks, use a timeline format. The AI will prioritize using a timeline when explaining coroutines and Tasks. </USER_SUMMARY>  <EPISODES> Episodes`

### G20 - mixed

`<SHORT_TERM> <SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Filler about dashboard widgets. | assistant: Filler. | user: Filler about CSS variables. | assistant: Filler. | user: Filler about copy review. | assistant: Filler. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. </DURABLE_NOTES> <RECENT_TURNS> user: Filler about empty charts. assistant: Filler. user: Filler about telemetry. assistant: Filler. user: Filler about a11y labels. assistant: Filler. </RECENT_TURNS> </SHORT_TERM>`
