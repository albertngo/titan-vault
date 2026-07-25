---
type: platform
status: active
last_activity: 2026-07-25
---

# GHL (GoHighLevel)

Titan's CRM: leads, SMS/email conversations, sales pipelines. Source of truth for
lead flow and deal stage. Read by `ghl-ingest`; written only by `ghl-actions`.

**Location:** Titan Flooring Inc. — `4BwjVRlyDCR4ZRdcSrFR` (America/Toronto)
**Access:** official HighLevel MCP server. Read-only Private Integration Token for
ingest/analysis; a separate write-scoped token is required for `ghl-actions` (not yet
issued). See `.mcp.json` and `docs/ghl-mcp-setup.md` in titan-agents.

## Pipelines

| Pipeline | Stages |
|---|---|
| (1) PROJECT: Lead Qualification | New Lead → Far Out (Cold) → Later Date (Warm) → ASAP (Hot) |
| (2) PROJECT: Sales Pipeline | Meeting (Scheduled) → Postponed → **Project Won** |
| STORE: Material Pipeline | Quote Provided → +3d Follow-up (Auto) → +8d Final Follow-up (Auto) → Engaged → No Answer → Closed Won / Closed Lost |

## Quirks worth knowing

- `lastStatusChangeAt` is the real close timestamp; `updatedAt` drifts with any edit.
- Source values arrive unnormalized — `Store` and `store` are the same channel.
- Contact records often predate their opportunity by months (repeat customers), so
  "lead age" ≠ sales-cycle length. Use opportunity `createdAt` for cycle time.
- Appointments appear as `TYPE_ACTIVITY_APPOINTMENT` events in the conversation
  stream, not as a separate object. Body prefix `Visit:` = in-home, `Store:` = in-store.
- Only ~1% of logged touches are automated; the funnel is manual today.

## Win-timeline findings — 2026-07-25

Full analysis of 297 won opportunities ($2.40M), 2023-07 → 2026-07. Method and
re-run instructions: `docs/ghl-analysis-framework.md` in titan-agents.

**Cycle time:** median deal cycle 13.8d (opportunity created → won); p75 31.5d.
Lead-age median 27.7d is inflated by repeat customers (23% of wins).

**Follow-up windows by source** (p75 = keep leads active at least this long):

| Source | Wins | Value | Deal median | Follow-up window | Touches |
|---|---|---|---|---|---|
| Store (walk-in) | 201 | $1.60M | 12.8d | ~4 weeks | 35 |
| Meta Ad | 61 | $491K | 20.8d | ~7 weeks | 56 |
| Tradeshow | 4 | $58K | 135d | 6+ months (nurture) | 56 |
| Contractor / repeat | 3 | $21K | ~0d | none — closes on relationship | 148 |

**Appointments are the hinge.** 59% of wins booked one, a median 1.6 days after the
lead arrived, after only 3–5 touches. The work is *after* the appointment: median 16
more days and ~40 more touches to close. Appointment-path deals are worth up to ~3×
more (in-store median $17.5K vs $5.5K with no appointment).

**Workload:** ~52 touches per closed deal, 76% SMS, 99% manual. First-reply median
1.7h but p75 26h — the slow tail is the cheapest available lever.

**Caveat:** won-only view. A source can look fast because its slow leads die rather
than close. Pair with a lost-deal pull before spend decisions.

## Log

- 2026-07-25 — Wired GHL MCP (read-only PIT). Ran first `ghl-ingest`. Completed
  win-timeline + activity analysis over all 297 won opportunities; findings above.
