# Lab 17 Golden Set Report

- Implementation: `student`
- Kind: `golden`
- Cases: **20**
- Passed: **20/20**
- Evidence hit rate: **100.0%**
- Average retrieval latency: **1194.6 ms**
- Average token reduction vs full source context: **13.9%**
- Golden bonus: **10/10** (100% required)

| Case | Layer | Pass | Latency ms | Retrieved tokens | Token reduction | Missing / Error |
| --- | --- | --- | ---: | ---: | ---: | --- |
| G01 | short_term | PASS | 0.4 | 227 | 0.0% |  |
| G02 | short_term | PASS | 0.0 | 133 | 0.0% |  |
| G06 | long_term | PASS | 1643.8 | 820 | 0.0% |  |
| G09 | semantic | PASS | 314.8 | 148 | 67.8% |  |
| G10 | semantic | PASS | 327.3 | 95 | 79.3% |  |
| G14 | mixed | PASS | 1821.5 | 431 | 0.0% |  |
| G03 | long_term | PASS | 1729.2 | 1383 | 0.0% |  |
| G04 | long_term | PASS | 1438.1 | 1380 | 0.0% |  |
| G07 | episodic | PASS | 382.5 | 274 | 0.0% |  |
| G08 | episodic | PASS | 292.5 | 292 | 0.0% |  |
| G11 | mixed | PASS | 1684.8 | 439 | 22.3% |  |
| G13 | mixed | PASS | 502.9 | 406 | 28.1% |  |
| G15 | mixed | PASS | 1990.3 | 736 | 0.0% |  |
| G16 | mixed | PASS | 1732.2 | 484 | 14.3% |  |
| G17 | mixed | PASS | 1789.0 | 484 | 14.3% |  |
| G18 | mixed | PASS | 662.3 | 440 | 22.1% |  |
| G19 | mixed | PASS | 1867.0 | 581 | 0.0% |  |
| G05 | long_term | PASS | 1515.0 | 1377 | 0.0% |  |
| G12 | mixed | PASS | 2125.4 | 468 | 25.9% |  |
| G20 | mixed | PASS | 2073.0 | 609 | 3.6% |  |

## Evidence excerpts

### G01 - short_term

`<SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. | assistant: Noted staging constraint. | user: Filler A about button padding. | assistant: Filler A. | user: Filler B about color tokens. | assistant: Filler B. | user: Filler C about copy tone. | assistant: Filler C. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. - user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. - assistant: Noted staging constraint. </DURA`

### G02 - short_term

`<RECENT_TURNS> user: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. assistant: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. user: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. assistant: Toi se uu tien timeline khi giai thich coroutine va Task. user: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. </RECENT_TURNS>`

### G06 - long_term

`FACT: Da hieu: LOTUS-88 uses Java for backend examples. [valid_at=2026-08-01T11:00:20Z, invalid_at=None] FACT: Lan Tran does not use Python in the LOTUS-88 backend example. [valid_at=2026-08-01T11:00:00Z, invalid_at=None] FACT: Da hieu: LOTUS-88 uses Spring Boot for backend examples. [valid_at=2026-08-01T11:00:20Z, invalid_at=None] FACT: Lan Tran prioritizes Spring Boot for the LOTUS-88 project. [valid_at=2026-08-01T11:00:00Z, invalid_at=2026-08-01T11:00:20Z] FACT: Lan Tran's project is LOTUS-88. [valid_at=2026-08-01T11:00:00Z, invalid_at=None] FACT: Lan Tran prioritizes Java for the LOTUS-88 project. [valid_at=2026-08-01T11:00:00Z, invalid_at=2026-08-01T11:00:20Z] <USER_SUMMARY> Lan's proje`

### G09 - semantic

`EPISODE: For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3. EPISODE: Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL. EPISODE: Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodic 3 percent, semantic 3 percent; trim lower-priority memory first. Marker: BUDGET-10-4-3-3.`

### G10 - semantic

`EPISODE: Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL. EPISODE: Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodic 3 percent, semantic 3 percent; trim lower-priority memory first. Marker: BUDGET-10-4-3-3.`

### G14 - mixed

`<LONG_TERM> FACT: Da hieu: LOTUS-88 uses Java for backend examples. [valid_at=2026-08-01T11:00:20Z, invalid_at=None] FACT: Lan Tran does not use Python in the LOTUS-88 backend example. [valid_at=2026-08-01T11:00:00Z, invalid_at=None] FACT: Da hieu: LOTUS-88 uses Spring Boot for backend examples. [valid_at=2026-08-01T11:00:20Z, invalid_at=None] FACT: Lan Tran's project is LOTUS-88. [valid_at=2026-08-01T11:00:00Z, invalid_at=None] FACT: Lan Tran prioritizes Spring Boot for the LOTUS-88 project. [valid_at=2026-08-01T11:00:00Z, invalid_at=2026-08-01T11:00:20Z] FACT: Lan Tran prioritizes Java for the LOTUS-88 project. [valid_at=2026-08-01T11:00:00Z, invalid_at=2026-08-01T11:00:20Z] <USER_SUMMARY>`

### G03 - long_term

`FACT: The personal demo ORCHID-27 prefers Python. [valid_at=2026-08-01T09:00:20Z, invalid_at=2026-08-05T08:00:00Z] FACT: Da hieu has a personal demo called ORCHID-27. [valid_at=2026-08-01T09:00:20Z, invalid_at=None] FACT: The personal demo ORCHID-27 avoids Java. [valid_at=2026-08-01T09:00:20Z, invalid_at=2026-08-05T08:00:20Z] FACT: Minh Nguyen's personal project is ORCHID-27. [valid_at=2026-08-01T09:00:00Z, invalid_at=2026-08-01T09:00:20Z] FACT: Minh Nguyen requires that the BLUEBIRD-42 project uses TypeScript with NestJS for the backend. [valid_at=2026-08-05T08:00:00Z, invalid_at=2026-08-05T08:00:20Z] FACT: Minh Nguyen references the ASYNC-FIX-20 incident. [valid_at=2026-08-03T10:03:00Z, in`

### G04 - long_term

`FACT: Minh Nguyen's personal project is ORCHID-27. [valid_at=2026-08-01T09:00:00Z, invalid_at=2026-08-01T09:00:20Z] FACT: Minh Nguyen requires that the BLUEBIRD-42 project uses TypeScript with NestJS for the backend. [valid_at=2026-08-05T08:00:00Z, invalid_at=2026-08-05T08:00:20Z] FACT: Minh Nguyen states that Python is not to be used for the backend of the BLUEBIRD-42 project. [valid_at=2026-08-05T08:00:00Z, invalid_at=2026-08-05T08:00:20Z] FACT: Minh Nguyen references the ASYNC-FIX-20 incident. [valid_at=2026-08-03T10:03:00Z, invalid_at=None] <USER_SUMMARY> The user's personal project is named ORCHID-27, for which they prefer to use Python. For the company project BLUEBIRD-42, the backend `

### G07 - episodic

`EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. EPISODE: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Hay kiem tra connection pool, lifecycle cua client va concurrency. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh l`

### G08 - episodic

`EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. EPISODE: Toi se uu tien timeline khi giai thich coroutine va Task. EPISODE: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Hay kiem tra connection pool, lifecycle cua client va concurrency. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection ch`

### G11 - mixed

`<LONG_TERM> FACT: Minh Nguyen references the ASYNC-FIX-20 incident. [valid_at=2026-08-03T10:03:00Z, invalid_at=None] FACT: Minh Nguyen's personal project is ORCHID-27. [valid_at=2026-08-01T09:00:00Z, invalid_at=2026-08-01T09:00:20Z] FACT: The benchmark report has the identifier LAB-REPORT-1600. [valid_at=2026-08-01T09:04:00Z, invalid_at=None] FACT: Minh Nguyen states that Python is not to be used for the backend of the BLUEBIRD-42 project. [valid_at=2026-08-05T08:00:00Z, invalid_at=2026-08-05T08:00:20Z] FACT: Minh Nguyen requires that the BLUEBIRD-42 project uses TypeScript with NestJS for the backend. [valid_at=2026-08-05T08:00:00Z, invalid_at=2026-08-05T08:00:20Z] <USER_SUMMARY> The user's`

### G13 - mixed

`<EPISODIC> EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. EPISODE: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Hay kiem tra connection pool, lifecycle cua client va concurrency. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: `

### G15 - mixed

`<LONG_TERM> FACT: Minh Nguyen references the ASYNC-FIX-20 incident. [valid_at=2026-08-03T10:03:00Z, invalid_at=None] FACT: Minh Nguyen's personal project is ORCHID-27. [valid_at=2026-08-01T09:00:00Z, invalid_at=2026-08-01T09:00:20Z] FACT: Minh Nguyen states that Python is not to be used for the backend of the BLUEBIRD-42 project. [valid_at=2026-08-05T08:00:00Z, invalid_at=2026-08-05T08:00:20Z] FACT: Minh Nguyen requires that the BLUEBIRD-42 project uses TypeScript with NestJS for the backend. [valid_at=2026-08-05T08:00:00Z, invalid_at=2026-08-05T08:00:20Z] <USER_SUMMARY> The user's personal project is named ORCHID-27, for which they prefer to use Python. For the company project BLUEBIRD-42, `

### G16 - mixed

`<LONG_TERM> FACT: Da hieu has a personal demo called ORCHID-27. [valid_at=2026-08-01T09:00:20Z, invalid_at=None] FACT: The benchmark report has the identifier LAB-REPORT-1600. [valid_at=2026-08-01T09:04:00Z, invalid_at=None] FACT: Minh Nguyen's personal project is ORCHID-27. [valid_at=2026-08-01T09:00:00Z, invalid_at=2026-08-01T09:00:20Z] FACT: Minh Nguyen references the ASYNC-FIX-20 incident. [valid_at=2026-08-03T10:03:00Z, invalid_at=None] FACT: Minh Nguyen requires that the BLUEBIRD-42 project uses TypeScript with NestJS for the backend. [valid_at=2026-08-05T08:00:00Z, invalid_at=2026-08-05T08:00:20Z] FACT: Minh Nguyen states that Python is not to be used for the backend of the BLUEBIRD-4`

### G17 - mixed

`<LONG_TERM> FACT: Minh Nguyen references the ASYNC-FIX-20 incident. [valid_at=2026-08-03T10:03:00Z, invalid_at=None] FACT: Minh Nguyen requires that the BLUEBIRD-42 project uses TypeScript with NestJS for the backend. [valid_at=2026-08-05T08:00:00Z, invalid_at=2026-08-05T08:00:20Z] FACT: Minh Nguyen states that Python is not to be used for the backend of the BLUEBIRD-42 project. [valid_at=2026-08-05T08:00:00Z, invalid_at=2026-08-05T08:00:20Z] FACT: Minh Nguyen's personal project is ORCHID-27. [valid_at=2026-08-01T09:00:00Z, invalid_at=2026-08-01T09:00:20Z] <USER_SUMMARY> The user's personal project is named ORCHID-27, for which they prefer to use Python. For the company project BLUEBIRD-42, `

### G18 - mixed

`<EPISODIC> EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. EPISODE: Toi se uu tien timeline khi giai thich coroutine va Task. EPISODE: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Hay kiem tra connection pool, lifecycle cua client va concurrency. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout thresho`

### G19 - mixed

`<LONG_TERM> FACT: Minh Nguyen requires that the BLUEBIRD-42 project uses TypeScript with NestJS for the backend. [valid_at=2026-08-05T08:00:00Z, invalid_at=2026-08-05T08:00:20Z] FACT: Minh Nguyen references the ASYNC-FIX-20 incident. [valid_at=2026-08-03T10:03:00Z, invalid_at=None] FACT: Minh Nguyen's personal project is ORCHID-27. [valid_at=2026-08-01T09:00:00Z, invalid_at=2026-08-01T09:00:20Z] FACT: Minh Nguyen states that Python is not to be used for the backend of the BLUEBIRD-42 project. [valid_at=2026-08-05T08:00:00Z, invalid_at=2026-08-05T08:00:20Z] FACT: The personal demo ORCHID-27 avoids Java. [valid_at=2026-08-01T09:00:20Z, invalid_at=2026-08-05T08:00:20Z] FACT: The personal demo O`

### G05 - long_term

`FACT: Minh Nguyen states that Python is not to be used for the backend of the BLUEBIRD-42 project. [valid_at=2026-08-05T08:00:00Z, invalid_at=2026-08-05T08:00:20Z] FACT: Minh Nguyen requires that the BLUEBIRD-42 project uses TypeScript with NestJS for the backend. [valid_at=2026-08-05T08:00:00Z, invalid_at=2026-08-05T08:00:20Z] FACT: Minh Nguyen's personal project is ORCHID-27. [valid_at=2026-08-01T09:00:00Z, invalid_at=2026-08-01T09:00:20Z] FACT: ORCHID-27 uses Python. [valid_at=2026-08-05T08:00:20Z, invalid_at=None] FACT: The personal demo ORCHID-27 prefers Python. [valid_at=2026-08-01T09:00:20Z, invalid_at=2026-08-05T08:00:00Z] FACT: Minh Nguyen references the ASYNC-FIX-20 incident. [vali`

### G12 - mixed

`<LONG_TERM> FACT: Minh Nguyen requires that the BLUEBIRD-42 project uses TypeScript with NestJS for the backend. [valid_at=2026-08-05T08:00:00Z, invalid_at=2026-08-05T08:00:20Z] FACT: Minh Nguyen states that Python is not to be used for the backend of the BLUEBIRD-42 project. [valid_at=2026-08-05T08:00:00Z, invalid_at=2026-08-05T08:00:20Z] FACT: BLUEBIRD-42 uses NestJS. [valid_at=2026-08-05T08:00:20Z, invalid_at=None] FACT: BLUEBIRD-42 uses TypeScript. [valid_at=2026-08-05T08:00:20Z, invalid_at=None] FACT: Minh Nguyen's personal project is ORCHID-27. [valid_at=2026-08-01T09:00:00Z, invalid_at=2026-08-01T09:00:20Z] FACT: The benchmark report has the identifier LAB-REPORT-1600. [valid_at=2026-`

### G20 - mixed

`<SHORT_TERM> <SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Filler about dashboard widgets. | assistant: Filler. | user: Filler about CSS variables. | assistant: Filler. | user: Filler about copy review. | assistant: Filler. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. </DURABLE_NOTES> <RECENT_TURNS> user: Filler about empty charts. assistant: Filler. user: Filler about telemetry. assistant: Filler. user: Filler about a11y labels. assistant: Filler. </RECENT_TURNS> </SHORT_TERM>`
