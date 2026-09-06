# Refactor notes — 2026-09-06

Branch: `refactor/ksm-a2a-directive`

## What changed

Aligned collab-mem with the A2A checkout + card-directive KSM model agreed in
the Tony / Grok session on 2026-09-06.

| File | Change |
| --- | --- |
| `ROSTER.md` | Rae = KSM on M4 (was "Claude Code on the M4"); Janet = isolated guardian on MBP (was "MacBook Pro 2016, future delegated"); Brett added as chief of staff; Grokbot added as cloud-facing A2A client. Repo identity corrected. |
| `MASTER.md` | M20 rewritten for A2A + directive; M21/M22/M23 added (directive MVP, v2 chat, Janet digest). M2 marked done. |
| `FACTS.md` | Dated section rewritten 2026-09-06: topology, Rae/Janet/Grokbot/Brett roles, checkout model, archive rule, port taxonomy, break-glass. |
| `CARD-CONTRACT.md` | v3: A2A checkout/check-in, card directive (section 8), Janet async audit, Grokbot as A2A client, visibility rule. |
| `projects/kanban-surface.md` | Repo corrected to anwhelan01/kanban-surface; outstanding/next updated for Brett reconfiguration + Grokbot A2A connect. |
| `docs/REFACTOR-NOTES.md` | This file. |

## What was deliberately left alone

- `LOG.md` — historical record; not rewritten.
- `daily/` — frozen at 2026-08-05; the next EOD ritual should generate 2026-09-06
  reflecting the new topology.
- `docs/board-state.md` — machine-rendered; left untouched.
- Other project cards (`chadai.md`, `ask-ebbi-uat.md`, etc.) — not in scope for
  this refactor; they still cite historical paths where relevant.

## Open decisions for Tony

1. Confirm the non-default A2A port Rae publishes (currently unspecified beyond
   "not 9900").
2. Confirm Janet's digest cadence (monthly assumed) and emergency-ping threshold.
3. Gate `APPROVE:desk-os-drill` before merging CARD-CONTRACT v3.
