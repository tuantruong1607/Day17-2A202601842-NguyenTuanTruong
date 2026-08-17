# Lab 17 — Multi-Memory Agent với Zep

11/11 PASS (100%); no-memory 2/11 (18.2%). Nguồn: `reports/benchmark.json`, `reports/comparison.md`.

Thiết kế theo paper Zep ([arXiv:2501.13956](https://arxiv.org/abs/2501.13956)): Search(φ) → Reranker(ρ) → Constructor(χ). φ/ρ trong `graph.search`; `render_graph_search` là χ cấp layer, `ContextBudgetManager` là χ cấp agent.

## 3 câu thực hành

1. **Layer quan trọng nhất: long-term** — 4 case, 20/56đ (E02, E03, E08, E09), gánh cả preference, open loop, conflict thời gian và user isolation.
2. **Zep vs Redis+Qdrant:** Zep bi-temporal — Python→TypeScript chỉ set `t_invalid` chứ không xoá edge cũ, nên giữ provenance. Qdrant chỉ cosine: hai fact mâu thuẫn nằm sát nhau, phải tự build versioning + TTL. Zep hybrid cosine + BM25 nên giữ được mã literal `PAYMENT-RULE-3` mà vector store thuần sẽ mù. Giá: ingestion bất đồng bộ (`wait_for_search`), lệ thuộc managed service.
3. **Guardrail poisoning:** `privacy_guard` bắt `memory_opt_in` + redact PII trước khi ghi durable; `MEMORY_SCHEMA` bắt mọi record mang `source`/`timestamp`/`validity` nên fact bịa lộ vì thiếu provenance; `heartbeat` chỉ dedupe / đánh dấu stale / recap, **không** tự thêm instruction vào durable memory.

## 4 câu phân tích

1. Không layer nào thấp: cả 4 đạt 100%. Baseline no-memory 0% ở mọi layer trừ short-term.
2. Nhiều token nhất: **E02 (1390)**, rồi E03 (1378), E08 (1340) — cả ba là long-term chạy đơn lẻ, không đi qua budget nên giữ nguyên Context Block + facts.
3. **E07 = long-term + semantic.** Evidence bắt buộc: `Python` (Context Block) và `Idempotency-Key` (standalone graph). Budget cắt long-term 1381→324 token; `Python` sống sót vì marked-facts + Context Block đứng trước, `trim()` giữ phần đầu — đảo thứ tự là fail.
4. Student giảm 19.1% token, no-memory giảm 81.8% nhưng hit rate chỉ 18.2%: no-memory rẻ vì không retrieve gì cả. Reduction một mình là chỉ số vô nghĩa. Paper Zep: 1.6k vs 115k token (−98.6%) mà accuracy vẫn tăng 55.4%→63.8%. Quyết định là *retrieve đúng*, không phải *retrieve ít*.

## E08 recency & E10 compaction

**E08** là dạng knowledge-update — loại duy nhất Zep thua full-context (−3.36%) vì Context Block tóm tắt mất dấu invalidation. Nên `retrieve_long_term` thêm `scope="edges", limit=20` để lấy `valid_at`/`invalid_at`. Khớp conflict rule của `MEMORY.md`: constraint mới theo scope project override preference chung, không xoá cái cũ.

**E10:** hạ `max_recent_messages` 6→4, raw turn bị evict nhưng `REVIEW-DEADLINE-1600`/`Friday`/`16:00` vẫn còn nhờ `extract_durable_notes` đẩy constraint lên summary. Buffer không đủ vì token tăng tuyến tính, tràn context là mất deadline.
