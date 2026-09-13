---
name: q
description: OPTIMAL EXECUTION PIPELINE v2 (bounded) - concise dialectic, fact gate, self-correcting loop.
---

# /q - OPTIMAL EXECUTION PIPELINE (v2, bounded)

## PHASE 1 - REASON (concise)
- Decompose: constraints, edge cases, deps, failure modes, success criteria - a few lines.
- State ONE primary approach. Only if genuinely ambiguous, add ONE alternative (one line).
- Optional dialectic (ONLY when a decision is truly contested): 1-line thesis, 1-line antithesis, 1-line synthesis. Do NOT write essays.
- FACT GATE: any fact/number/date/citation/API signature -> verify via web_search/web_fetch. Primary sources only (official docs, repos, papers). Reject SEO spam, affiliate hubs, content farms. Unconfirmed -> label unconfirmed.

## PHASE 2 - AUTONOMOUS ACTION
- Execute tools immediately (run_command/read_file/write_file/list_files/web_search/web_fetch). No user confirmation for server actions.
- Non-interactive shell only. No TTY prompts.
- Read before write. Inspect real state; never assume file contents or paths.
- Minimal output (head/tail/grep/wc). Never dump full logs.

## PHASE 3 - VERIFY & SELF-CORRECT
- Verify empirically: code -> tests/linter/logs; facts -> re-check primary source; files -> re-read and confirm.
- On failure (max 2 retries per issue): memory_save(type=feedback, tags=[failure-log, domain]) -> adjust -> re-execute.
- Check prior failure-logs first. Do NOT repeat known mistakes.

## BUDGET & TERMINATION (hard)
- Max 8 tool calls per turn. On cap: STOP, emit short progress summary, hand back.
- Same failure twice -> STOP and report.
- No state change / no new info -> STOP and summarize.
- Never wait for user input mid-task, but never run unbounded.

## ANTI-HALLUCINATION
- Uncertain fact -> web_search. Cannot confirm -> unconfirmed. Never invent numbers, paths, citations.
- Apply domain checklists from memory (market data: CVD, order book imbalance, depth skew, spoofing detection).

## STALL RECOVERY
- If stalled or about to repeat: emit 'PROGRESS: ... / BLOCKED: ...' and STOP.
- A clean partial summary beats a stalled stream.
