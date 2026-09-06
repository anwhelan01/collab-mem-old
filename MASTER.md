# MASTER — the backlog (durable; daily lists hang off this)

> Each item has an id (M#), a one-line description, an owner, and a status.
> Statuses used here include `backlog` · `active` · `blocked` · `blocked on Tony`
> · `needs-decision` · `paused` · `done` · `superseded` · `later`. Done items
> drop to LOG.md; combined labels such as `done / superseded` preserve history.

| id | Item | Owner | Status | Notes |
|----|------|-------|--------|-------|
| M2 | **Seat Grok in collab-mem** — add to ROSTER, agree the Rae/Grok ownership split + read/write protocol | Rae | done → drops to LOG | Grokbot is now the cloud-facing A2A client; Rae is KSM. Protocol locked in CARD-CONTRACT v3. |
| M3 | **ChadAI Step 4 — data sources + channel** — legislation.gov.uk API + Scrapling MCP + NotebookLM MCP + FB frame; answer-only-from-notebook | Rae | **blocked on Tony** | Plan/flow are in the external ChadAI repository; see `projects/chadai.md` before resuming. **5 decisions await Tony** (see 2026-05-31 daily). Also fixes the X-SAR ungrounded-citation gap. |
| M4 | **ChadAI Step 5 — full hold-nothing purge** — wipe `state.db` rows + `sessions/` + `pairing/` + uploads + email address at session end; server-side, guaranteed | Rae | backlog | The spec is in the external ChadAI repository; do not assume the former VPS path is live. |
| M5 | **Wire collab-mem ↔ ChadAI/HANDOFF.md** — one canonical entry point, no drift | Rae | backlog | Deep cursor and current runtime boundary are recorded in `projects/chadai.md`; former host paths are historical until Tony reopens the project. |
| M6 | **Top-tier model for Chad** — once a working inference key is on the box, move Chad off Nemotron | Tony | later | Blocked on a key; see FACTS → Models. |
| M7 | **ChadAI Stage-2 — self-hosted grounded notebook** to close the NotebookLM third-party GDPR gap | Rae | later | Post-MVP hardening. |
| M8 | **Chad instruction polish + paid-tier lines (from the X-SAR case)** — Art 22/15(1)(h) spearhead, export-rebuttal line, escalation ladder (s.165 DPA), dispute-letter drafting (paid). Pin the answer-walkthrough | Tony / Rae | backlog | Source is external: `ChadAI/docs/cases/x-suspension-sar.md` in the ChadAI repository. Free = strategy; Paid = the counter-play. |
| M9 | **GitHub estate audit + doctrine pick** — classify all 37 k3ss-official repos; pick 4–6 week lane (cash + strategic) on operator-doctrine terms (leverage / revenue path / reuse / distribution / mess cost / momentum). Park merch/music/DJ; consolidate AgentOS sprawl | Rae | done → drops to LOG | Output: 37-repo matrix + execution arc + last-30-min reconciliation in the Perplexity task at <https://www.perplexity.ai/computer/tasks/b74d4915-8608-4979-bb01-77e1221c9957>. Picks: Socialite (cash) + 3to5er (strategic) on M4 + VPS-1/2. |
| M10 | **Repo hygiene (8 archives, 5 pins)** — archive 8 dead repos (thread-to-pdf, quiet-alpha-v2, social-machine, looper, soul_architecture, flowith-docs, quiet_alpha, stock_oracle); pin Socialite / 3to5er-agentos / scam-alertuk-chad / titan / tanks-hud | Rae | active | Hour-0–1 block, 2026-06-06. tanks-hud kept in pins after re-audit found Tony pushed real features at 19:48 UTC tonight. |
| M11 | **AgentOS consolidation** — collapse the 5-repo sprawl into `3to5er-agentos/` as source of truth: `runtime/` ← hermes-agentos-starter-kit; `verticals/dental-uk/` ← vertical-experts-agentos; planning content folded later. Rule for the week: zero new `*-agentos` repos from Rae | Rae | active | Colocate, don't refactor. Compiler `scripts/compile_pack.py` ships in this MASTER item (D6). |
| M12 | **Socialite Field Closer Pack v0 → first paying Pokhara client** — `pack.py` generator (5-page PDF) + `field.socialite.design/<lead-id>` pocket UI + Sunday's 10-visit field push. NPR 8k/15k/25k tiers, 2 months upfront, cash/eSewa/Khalti | Rae + Tony + field team | active | Cash-flow-now lane. Sunday gate = ≥1 closed deal. |
| M13 | **Ghost as Socialite Outreach session layer** — drop Ghost in as FB Messenger backend (reuse X-adapter shape). One repo, multiple consumers: Socialite Outreach, Scout recon, future Chad evidence runs, 3to5er Tactical Funnel | Rae | active | Hour-4–5 block, 2026-06-06. LinkedIn adapter scheduled Tuesday. |
| M14 | **Titan as intelligence service for downstream products** — add Nepal SMB FB signals collector → feeds Socialite Scout. Treat Titan as a primitive other products call, not a product to sell | Rae | active | Sunday parallel-work block. |
| M15 | **3to5er operator-pack #2 — UK vertical** — dental (Chorley) or planning consultants (Lancaster), decided on warmer first-five-calls list. Pack v1 compiler must produce it with ≤50% manual work | Rae + Tony | backlog | Tuesday–Wednesday (Day 4–5). Sprint readiness gate. |
| M16 | **ScamAlert Trinity wiring** — Machine Phase 2 → Dashboard → Chad. Activate as the next sprint AFTER Socialite is paying AND Tony unblocks ChadAI M3. Background ingest only this sprint | Rae | later | Date dropped — depends on Tony's M3 decisions, not a calendar date. Tony has been pushing to scam-alertuk-chad branch tonight; real timeline is in his head. |
| M17 | **`chadai` repo triage** — Tony imported "The AI Guy" (Nate's Substack curation: 39 prompts + Adversarial Assistant / Workflow Architect / Content Engine kit) into a new private repo 2026-06-05 23:06 UTC. Decide: stash-only, feed into Chad v6 prompt when M3 reopens, or stand up as standalone product | Tony | needs-decision | Three-option question is on 2026-06-06 daily. Rae assumes stash-only until told otherwise. |
| M18 | **Ask Ebbi UAT — the Planning Oracle** — Hermes-native Ask Ebbi product, Library MCP and active private UAT. Card: `projects/ask-ebbi-uat.md` | Tony + Rae | **active UAT** | Private `k3ss-official/ask-ebbi-uat/main` is reconciled byte-for-byte with tracked source on `alwyzon-1`; snapshot `1c3d257`. Container `ebbi` remains healthy behind Cloudflare Access. Continue Tony/Rae UAT. |
| M19 | **Historical two-tenant VPS placement** — ChadAI and Ask Ebbi as peer Docker projects | Tony | **done / superseded** | The July ChadAI+Ask Ebbi plan remains superseded. Current state is different: KSM is host-native systemd and Ask Ebbi alone uses Docker for private UAT; ChadAI is absent. |
| M20 | **Kanban Surface Manager — A2A checkout + card directive over collab-mem** — Rae (M4 Hermes) is KSM; workers check out cards directly over A2A; the card directive (comment + legal-move dropdown + scoped @mentions, one send) replaces free-text comments; Janet audits async. Card: `projects/kanban-surface.md` | Rae | **active** | Repo corrected to `anwhelan01/kanban-surface`. PRs #2 (MVP directive) and #3 (v2 chat backlog) open. Next = Brett reconfigures Rae per the specs; Grokbot connects as A2A client. |
| M21 | **Card directive MVP** — ship the comment box + legal-move dropdown + scoped @mentions on kanban-surface (PR #2) | Brett | active | Replaces free-text comments. One send = post + move. Rae woken only by @mention. |
| M22 | **Card chat surface v2** — real-time per-card threads, @everyone, live updates, full-screen view (PR #3, lands after #2) | Brett | backlog | Parked until the directive MVP proves the flow. |
| M23 | **Janet monthly digest** — async summary of board state for Brett; emergencies ping directly | Janet | active | No firehose. Brett reads on his own schedule. |

> **2026-08-05 supersession:** M19 records a completed historical topology, not
> current host state. `alwyzon-1` now runs host-native KSM plus one isolated Ask
> Ebbi Docker UAT workload; ChadAI remains absent. See FACTS, M18 and M20.
>
> **2026-09-06 refactor:** M20 rewritten for the A2A checkout + card-directive
> model. Rae is KSM (not Codex); Janet is the isolated guardian; Brett is the
> outside-Hermes orchestrator; Grokbot is the cloud-facing A2A client. Repo
> identity corrected to `anwhelan01/kanban-surface`.

## ChadAI build roadmap
1. Hermes install — ✅ done
2. Hold-nothing config — ✅ done + verified
3. Agents as skills (Chad / Retriever / Auditor) — ✅ done + smoke-tested + validated on a real case
4. Data sources + channel — ◐ M3 (plan + flow ready; awaiting Tony's 5 decisions)
5. Full hold-nothing purge + end-to-end test — ◐ M4

Canonical specs are external to this repository in `ChadAI/docs/`:
`session-flow.md` (the session), `step4-plan.md` (the wiring), and
`cases/x-suspension-sar.md` (the validation fixture). See `projects/chadai.md`
for the current boundary before using those paths.
