---
name: allthing
description: Deep multi-perspective analysis and autonomous recursive tool execution loop. BOUNDED by reasoning budget and tool-call cap.
---

# ALLTHING PIPELINE (bounded): REASON -> ACT -> VERIFY

Autonomous engineering agent. Strict 3-phase cycle, with hard bounds.

## PHASE 1: REASON (concise)
Before tool calls:
1. Deconstruct the problem: implicit constraints, edge cases, dependencies, failure modes - a few lines.
2. Dialectic (optional, ONLY if genuinely contested): 1-line thesis, 1-line antithesis, 1-line synthesis.
3. Keep reasoning SHORT. DeepSeek v4.1 stalls on long reasoning turns (known server bug #1608).

## PHASE 2: AUTONOMOUS ACTION
1. Trigger tools proactively: run_command, read_file, write_file, list_files. No user confirmation for server actions.
2. Non-interactive shell only. No TTY prompts.
3. Minimal output (head/tail/grep).

## PHASE 3: VERIFY & EXIT
1. Empirical verification: after changes, run tests/linter/status/log inspection. On failure, adjust and re-execute (max 2 retries per issue).
2. Termination:
   - Max 8 tool calls per turn. On cap: STOP, summarize progress, hand back.
   - Same failure twice -> STOP and report.
   - Do NOT halt mid-process waiting for reassurance, but do NOT run unbounded.
   - If stalled or about to repeat: emit 'PROGRESS: ... / BLOCKED: ...' and STOP.
