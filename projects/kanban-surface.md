# Kanban Surface Manager — A2A checkout + card directive over collab-mem
STATUS: active        UPDATED: 2026-09-06 by refactor/ksm-a2a-directive

## What

Rae (M4 Hermes) is the Kanban Service Master. Workers and Grokbot check out
cards directly from her over A2A; she is the sole gatekeeper of collab-mem
writes. The card directive — comment box + legal-move dropdown + scoped
@mentions, one send — replaces free-text comments. Janet audits asynchronously
and falls back to KSM if Rae drops. collab-mem remains the canonical source for
project facts, priorities, history and ordered next actions.

## Where

- Active GitHub repo: `anwhelan01/kanban-surface` (private); historical
  `k3ss-official/kanban-surface` is superseded.
- Open PRs: #2 (card directive MVP), #3 (v2 chat backlog, lands after #2).
- Control host: M4 (Rae's Hermes install); Janet on a separate MacBook Pro.
- A2A endpoint: non-default port (not 9900); 9900 hits are Janet's tripwire.
- Access chain: Tailscale-first, Cloudflare tunnel fallback, local IP last.
- Scoped tokens: Rae (KSM), Janet (audit+fallback), Grokbot (orchestrator-tier,
  no archive). Each in its own 1Password vault entry.

## Done

- 2026-09-06 — Refactored collab-mem to match the A2A checkout + card-directive
  model: ROSTER, MASTER, FACTS, CARD-CONTRACT v3, this card. Repo identity
  corrected to anwhelan01/kanban-surface.
- 2026-09-04 — desk-os-drill: CARD-CONTRACT v2 drafted (Brett verified); seats
  recorded (Brett orchestrator, Rae KSM, Janet guardian).
- 2026-07-30 — Restored the original architecture after Tony corrected the KRP
  detour: Hermes native Kanban is the KSM, `kanban-surface` is active, and
  collab-mem remains project truth. PRs #1–#3 adapted Hermes v0.19, added the
  source-linked card panel, defined the KSM identity and added boot-safe units;
  all GitHub CI passed.
- 2026-07-30 — Deployed the exact merged `kanban-surface` release to the KSM
  host, created the named native board/project, installed five real cloned Hermes
  profiles, configured repo-scoped deploy keys, and passed all on-box offline
  suites against the real collab-mem schema.
- 2026-07-30 — Projected 28 live collab-mem objects into native cards with
  stable idempotency keys. The dispatcher remained off during import; a live
  version drift briefly reported the imported cards ready, so all 28 were
  parked before any worker ran. The second sync proved 0 duplicates and
  admitted exactly one card at WIP 1.
- 2026-07-30 — Opened the authenticated loopback surface in a real Chrome
  session through the SSH tunnel. The selected card displayed its full
  canonical source file, GitHub backlink and native receipt history.
- 2026-07-30 — Ran the first bounded native intake dispatch. It claimed,
  heartbeated and left receipts correctly, but treated an archived predecessor
  as a live duplicate. Rejected that routing result, fixed intake to ignore
  `done`/`archived` history, fixed the installer to create complete native
  profiles, and merged/deployed PR #4.
- 2026-07-30 — Replayed the same canonical work. Proved Hermes'
  `reassign --reclaim` and active-run archive primitives without a model,
  encoded exact terminal commands in all five profiles, and merged/deployed
  PR #5.
- 2026-07-30 — Activated the native gateway, UI, watcher and both timers. Locked
  the KSM to `max_in_progress=1`, `max_spawn=1`, one worker per profile,
  `auto_decompose=false`, and a 60-second dispatcher tick.
- 2026-07-30 — Closed two canonical-control gaps: project `next-N` references are
  now permanent (PR #6); ledger sync is projection-only by default with manual-only
  admission (PR #7).
- 2026-07-30 — Completed the strict host residue pass and two-boot acceptance.
  Removed the empty Docker/containerd stack and stale identities. Final checks
  found no KRP residue; all five native units and the loopback UI remained
  healthy.
- 2026-07-30 — Completed the first full production-shaped vertical slice.
  `KSM-PILOT-1` flowed through Hermes planning, KSM plan validation, Codex patch
  proposal, two explicit rejection gates, human correction, 15 passing tests,
  GitHub PR #2, merge, immutable deployment, and deterministic verification.

## Outstanding

- Brett reconfigures Rae from orchestrator to KSM per the specs (Tony's
  instruction; Rae never self-modifies).
- Grokbot connects as an A2A client to Rae's endpoint.
- Ship the card directive MVP (PR #2 on kanban-surface).
- Define the v2 chat surface (PR #3) after the directive proves the flow.

## Next

1. Brett: reconfigure Rae per CARD-CONTRACT v3 and the kanban-surface specs;
   explain the new flow; handle end to end. Escalate to Tony only on a blocker.
2. Grokbot: connect to Rae's A2A endpoint; verify one create-card round trip.
3. Ship PR #2 (card directive MVP); validate the one-send flow on a real card.
