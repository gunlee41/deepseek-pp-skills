---
name: q
description: OPTIMAL EXECUTION PIPELINE v3 (universal) - concise dialectic, fact gate, self-correcting loop, MCP tool-call protocol enforced.
---

# /q - OPTIMAL EXECUTION PIPELINE (v3, universal)

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

## MCP TOOL-CALL PROTOCOL (CRITICAL - repeated failure source)
- The extension ONLY executes the FULL prefixed tag name, e.g. `mcp_cfae624d_8424_4425_a0c4_2bb482c0b855_run_command` or `mcp_t_34c58f12_55be_49e2_ae8e_cfb9baec43f9_run_command`.
- Short aliases (`run_command`, `list_files`, etc.) are NOT executed. They render as plain text and the session looks frozen / stalled.
- NEVER append stray closing tags (`</parameter>`, `</invoke>`) after the JSON. That breaks XML parsing.
- Exact form: full-prefixed tag + pure JSON body + matching close tag, NOTHING after.
- When a tool call appears as text instead of executing: the cause is a wrong/short tag name. Switch to the full prefixed name and retry.
- Empty-args error (`must have required properties ... Received arguments: {}`) -> rewrite JSON cleanly, retry once.
- SSE probe: `:8001/sse` is a stream; always use `curl --max-time N` to avoid a 60s hang.
- SELF-CHECK before every tool call: (1) tag has `mcp_..._` prefix? (2) JSON valid and non-empty? (3) nothing after close tag? (4) non-interactive?

## ENVIRONMENT NOTES (home server)
- MCP server: /home/gunlee41/mcp-server/server.py - 3 transports: :8000 session-based, :8001 SSE, :8002 stateless+json_response (deepseek++ recommended).
- deepseek++ v4.1 is a stateless HTTP client -> prefer :8002/mcp.
- All MCP hosts (homeserver2, home server) point to the SAME machine (`pc`).
- server.log has RotatingFileHandler (5MB x3); TraceMiddleware payload logging capped at [:300].

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
