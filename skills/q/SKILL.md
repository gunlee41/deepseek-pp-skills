---
name: q
description: OPTIMAL EXECUTION PIPELINE v2 — dialectic synthesis + fact gate + self-correcting loop (improved /1).
---

# /q — OPTIMAL EXECUTION PIPELINE (v2, improved /1)

## PHASE 1 — REASON & DEBATE
- Decompose the problem: explicit constraints, implicit constraints, edge cases, dependencies, failure modes, and success criteria.
- Generate at least 2 competing hypotheses / approaches.
- DIALECTIC SYNTHESIS:
  - Thesis: state the initial approach and why it seems best.
  - Antithesis: attack it — strongest counter-argument, hidden risks, trade-offs, adversarial cases.
  - Synthesis: adopt the stronger branch OR fuse both into a higher-order strategy that resolves the contradiction. Record which branch won and why.
- FACT GATE: any fact, number, date, citation, or API signature → verify via web_search / web_fetch. Primary sources only (official docs, repos, papers). Reject SEO spam, affiliate hubs, content farms. If unconfirmed → label "unconfirmed".

## PHASE 2 — AUTONOMOUS ACTION
- Execute tools immediately (run_command / read_file / write_file / list_files / web_search / web_fetch). No user confirmation for physical server actions.
- Non-interactive shell only. No TTY prompts. Keep outputs minimal to conserve context.
- Read before write. Inspect real state; never assume file contents or paths.

## PHASE 3 — VERIFY & SELF-CORRECT
- Verify empirically: code → run tests / linter / logs; facts → re-check the primary source; files → re-read and confirm.
- On failure:
  1. Save root cause via memory_save(type=feedback, tags=["failure-log", <domain>]).
  2. Return to Phase 1, diagnose, adjust.
  3. Re-execute Phase 2.
- Before starting: check prior failure-logs from memory. Do NOT repeat known mistakes.
- Do NOT stop until fully verified. Only return the final summary when the task is complete and confirmed functional.

## ANTI-HALLUCINATION
- Uncertain fact → web_search. Cannot confirm → say "unconfirmed". Never invent numbers, paths, or citations.
- Apply domain checklists from memory (e.g., market data: CVD, order book imbalance, depth skew, spoofing detection).

## TERMINATION
- No mid-process halting, no waiting for user reassurance while the task is incomplete.
