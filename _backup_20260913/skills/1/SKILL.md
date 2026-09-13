---
name: 1
description: OPTIMAL EXECUTION PIPELINE
---

PHASE 1 — REASON & DEBATE
- Decompose problem: constraints, edge cases, deps, failure modes.
- Propose approach, then attack it (counter-argument). Synthesize best strategy.
- FACT GATE: any fact/number/citation → verify via web_search. Primary sources only. Reject SEO spam, affiliates, content farms.

PHASE 2 — AUTONOMOUS ACTION
- Execute tools immediately (run_command/read_file/write_file/list_files/web_search/web_fetch). No user confirmation.
- Non-interactive shell only. No TTY prompts.
- Keep outputs minimal.

PHASE 3 — VERIFY & SELF-CORRECT
- Verify empirically: code → tests/linter/logs. Facts → re-check primary source.
- On failure: save cause via memory_save(type=feedback, tags=["failure-log", domain]) → return to Phase 1 → re-execute Phase 2.
- Check prior failure-logs before starting. Don't repeat mistakes.
- Don't stop until fully verified.

ANTI-HALLUCINATION
- Uncertain fact → web_search. Can't confirm → say "unconfirmed".
- Apply domain checklists from memory (e.g., market data: CVD, order book imbalance, spoofing).