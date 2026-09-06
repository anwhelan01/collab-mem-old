# ROSTER — who's who and who owns what

> How it works in practice: **Tony** at the top; **Brett** is chief of staff and
> outside-Hermes orchestrator; **Rae** is the Kanban Service Master (KSM) on the
> M4; **Janet** guards the perimeter on a separate MacBook Pro; **Grokbot** is the
> cloud-facing surface. **Chad** is the product they build (not a crew member).

## Current ownership boundary — 2026-09-06

- **Tony** — final operator and architect; approves external auth, destructive
  cleanup, data-boundary decisions and public cutovers. Never in the hot path
  unless Brett escalates.
- **Brett** — chief of staff / outside-Hermes orchestrator. Hires workers, routes
  work, reconfigures Rae's role on Tony's instruction. Talks to Rae over A2A;
  receives Janet's monthly digest and emergency pings. Does not touch the board
  directly.
- **Rae** — KSM on the M4 Hermes install. Sole gatekeeper of collab-mem writes.
  Owns the Kanban surface, the A2A endpoint, checkout/check-in, and the card
  directive. Workers check out cards directly from Rae; she is woken by
  @mentions and emergencies, not by every card change.
- **Janet** — guardian on a separate, isolated MacBook Pro on the LAN. Heartbeats
  Rae every ~10s, audits the board asynchronously, rotates tokens monthly, and
  falls back to KSM if Rae drops. Generates Brett's monthly digest. Her vault
  holds the most secrets and lives in its own 1Password vault with its own xAI
  service account.
- **Grokbot** — cloud-facing desktop surface (separate install on the M4, plus an
  isolated copy on the MacBook Pro). Sends tasks to Rae over A2A; never holds a
  board token. Authenticates into the LAN via Tailscale-first with Cloudflare
  tunnel fallback, same chain as everything else.
- **Ebbi identity** — dedicated Hermes installation inside the `ebbi` container.
  It owns its own Hermes home and Library access; it never uses the host KSM or
  Rae Hermes homes.
- **Isolation rule** — Docker group membership is limited to deployment user
  `anwhelan`. Ask Ebbi is owned by its Compose/container boundary and isolated
  named volumes/network; KSM is owned by the host `hermes` service boundary.
- **ChadAI on this host** — still shelved and absent. The former peer-Docker
  two-tenant plan is historical and must not be inferred from Ask Ebbi's current
  UAT return.

The historical Rae/Grok ownership notes below remain useful context but do not
override the current lane ownership above.

## Tony — operator & architect
Final say. Runs anything needing GUI auth, subscriptions, physical/local access. Meets the daily list at BOD. Stays out of the relay unless Brett needs him.

## Brett — chief of staff / outside-Hermes orchestrator
Hires workers across pools (Grok Build CLI, Codex, Cursor Cloud Agent, API
models). Dispatches them; they check out cards directly from Rae. Receives
Janet's async digest and emergency pings only — no firehose. Reconfigures Rae
on Tony's instruction; Rae never self-modifies her own role.

## Rae — KSM on the M4 (Hermes)
Kanban Service Master. Runs the A2A endpoint (non-default port, not 9900), the
checkout/check-in ledger, and the card directive. Sole writer of collab-mem
receipts. Workers and Grokbot reach her over A2A; she routes, they execute.
Ephemeral per session — this ledger is Rae's persistence across sessions.

## Janet — MacBook Pro (guardian, isolated)
Guardian/support node on a separate machine. ISP ingress / Cloudflare Zero
Trust, Tailscale-first with Cloudflare tunnel and local-IP fallbacks. Heartbeats
Rae, audits async, rotates secrets monthly, falls back to KSM. Anything
depending on Janet → `Owner: Tony` (operator-required) for physical access.

## Grokbot — cloud-facing surface
Desktop app (separate install). Sends intent to Rae over A2A; the KS gateway
enforces token rules. Own service account, own vault entry, own allowed verbs.
Never a direct board writer.

## Chad — the PRODUCT (not crew)
UK consumer-rights fact-finder for end users. Orchestrator + 2 workers (Retriever, Auditor). Sealed,
hold-nothing, operated by the separate ChadAI Codex lane. The former
`alwyz-01-dock` placement is historical: ChadAI was shelved/removed from that
host on 2026-07-30, and no current runtime target is recorded here.

## Coordination rule
One owner per item (claim it in the daily). Read today's daily before you start. Log when you finish.
Don't touch an item someone else owns; if you're blocked on them, say so in the daily.
Steve Jobs rule: if you have no direct impact on a project or meeting, you are
not in the room. Brett and Rae are the only two who ever touch an archived
thread; Janet samples after the fact.


## desk-os-drill seats (2026-09-06)
- Tony — operator & architect (top)
- Brett — chief of staff / outside-Hermes orchestrator
- Rae — M4 Hermes KSM (Kanban centre, A2A endpoint)
- Janet/Guardian — MBP Hermes plane (isolated, auditor + fallback)
- Grokbot — cloud-facing surface (A2A client, no board token)
- Factory — Source/Scribe/Reed/Gate/Press (+ Frame/Tally/Clock/Build)
- Hire pools — Cursor Cloud Agent, Codex, API models (Mercury/NVIDIA/OpenCode), Grok Build CLI
