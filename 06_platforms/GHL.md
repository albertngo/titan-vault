---
type: platform
visibility: admin
status: active
last_activity: 2026-07-26
---

# GHL (GoHighLevel)

Titan's CRM: leads, SMS/email conversations, sales pipelines. Source of truth for
lead flow and deal stage. Read by `ghl-ingest`; written only by `ghl-actions`.

**Location:** Titan Flooring Inc. — `4BwjVRlyDCR4ZRdcSrFR` (America/Toronto)
**Access:** official HighLevel MCP server. Read-only Private Integration Token for
ingest/analysis; a separate write-scoped token is required for `ghl-actions` (not yet
issued). See `.mcp.json` and `.env.example` in titan-agents for the wiring and the
required scopes.

## Pipelines

| Pipeline | Stages |
|---|---|
| (1) PROJECT: Lead Qualification | New Lead → Far Out (Cold) → Later Date (Warm) → ASAP (Hot) |
| (2) PROJECT: Sales Pipeline | Meeting (Scheduled) → Postponed → **Project Won** |
| STORE: Material Pipeline | Quote Provided → +3d Follow-up (Auto) → +8d Final Follow-up (Auto) → Engaged → No Answer → Closed Won / Closed Lost |

## Stale thresholds (per stage, from the GHL workflow)

`stale_lead` is applied after this long in stage; if the same duration passes again
with the tag present, the opportunity is auto-**abandoned** (so abandonment = 2×).

| Stage | Stale | Abandoned |
|---|---|---|
| ASAP (Hot) | 7d | 14d |
| New Lead | 14d | 28d |
| Later Date (Warm) | 40d | 80d |
| Far Out (Cold) | 90d | 180d |
| Meeting (Scheduled) | 30d | 60d |
| Postponed | 90d | 180d |

Machine-readable copy: `config/ghl-workflow.json` in titan-agents — keep the two in
sync when a threshold changes in GHL.

**Consequence:** thresholds span 7–90 days, so raw days-in-stage is not comparable
across stages. A hot lead at day 5 (2 days left) is more urgent than a cold lead at
day 60 (30 days left). Rank by *percentage of threshold*, not elapsed days.

**Meeting-scheduled counts from stage entry, not from the appointment** — so an
appointment booked far out eats the window before follow-up can start. Measured
2026-07-25 across 52 contacts in stage: the typical lead books 3.7 days after entering
the stage, leaving a **26.3-day** effective window before the 30-day stale mark. In the
slowest 1-in-10 cases (p90) the visit is 8.1 days out, leaving only ~22.
One contact was already negative (−9.1d): tagged stale before the visit happens.
Design target for the not-yet-built sequence: **~3 touches inside 21 days post-visit**,
with an exception path for bookings >20 days out.

## ID reference

Everything is keyed by opaque IDs. These are the join keys between GHL, ingest files,
and vault notes — names are display only.

| ID | Example | Stored in vault? |
|---|---|---|
| `locationId` | `4BwjVRlyDCR4ZRdcSrFR` | in this note |
| `companyId` (agency) | `LL2yxboXpWK383YNA3ff` | no |
| `contactId` | `KZUIKMSTL7UHh46L8gVN` | ✅ `ghl_contact_id` |
| `opportunityId` | `e7hd18SsWP9MGBEcu3ez` | ✅ `ghl_opportunity_id` |
| `conversationId` | `WG8SqctPw5Hz1uSDZPxz` | no (ingest only) |
| `messageId` | `hlvEOHUn9MeIbHI5usai` (+ `altId` = provider/Twilio `SM…`) | no |
| `appointmentId` | `pLu0iVvx9ZNusiO6x8J0` | no |
| `pipelineId` | `ZxYBFNifUNNxU7xgQclg` | name only |
| `pipelineStageId` | `149635d1-3d6a-48c7-9198-7db80b2232b5` | name only |
| `calendarId` / `groupId` | `9wHcUAkAFKWUwN75TbtW` / `axmp8LcyMC4VyhhWce68` | no |
| `assignedUserId` | `rAMFCiXbAjJOEjtyyvmn` (Pourya Lalee) | no |
| `customFieldId` | `8xlNjiw1kf3MFNsII0jv` (~60 fields) | no |
| `scoreProfileId` | `6840ab5f91c5a1ccdfd54a20` | no |
| ad attribution | `campaignId` / `adSetId` / `adId`, numeric; `formId`/`mediumId` | no |

Pipeline and stage are stored as **names, not IDs** — a human can verify
`2. *Project Won*` and cannot verify `149635d1-…`. The opportunity ID is the anchor;
everything else is reachable from it.

**Three ID formats, and the trap:**

```
20-char alphanumeric    KZUIKMSTL7UHh46L8gVN     contacts, opportunities, conversations,
                                                 messages, pipelines, calendars, users
UUID with dashes        149635d1-3d6a-48c7-…     pipeline STAGES only
24-char hex             6840ab5f91c5a1ccdfd54a20 score profiles
numeric string          120216224215840296       Meta/Google ad IDs
```

Any ID-validation rule assuming 20 chars silently rejects every stage ID. Conversely,
a dashed UUID where a contact ID belongs means something got crossed.

Tags are plain strings, not IDs. `traceId` / `mcp_trace_id` are per-request debugging
values — never store them.

**Provenance trap:** in ingest output, `workflow_drift[].ref` holds a contact **or** a
conversation ID depending on the finding type. Take contact IDs from a record's
explicit `contact_id` field, never from `ref`.

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

**Reading the percentiles below.** *median* (p50) = half are faster, half slower — the
normal case. *p75* = 3 of every 4 are within this. *p90* = 9 of every 10 are within
this. The median tells you what usually happens; the p75/p90 tells you how bad the slow
cases get. Plan around the median, make promises against the p75/p90.

**Cycle time:** half of won deals close within 13.8d (opportunity created → won), and
three out of four within 31.5d — so 1 in 4 takes longer than a month.
Lead-age median 27.7d is inflated by repeat customers (23% of wins).

**Follow-up windows by source** — each window covers 3 of every 4 wins from that source
(p75). Drop a lead sooner and you're discarding deals that would have closed:

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

**Workload:** ~52 touches per closed deal, 76% SMS, 99% manual. A typical lead gets its
first reply in 1.7h, but 1 in 4 waits more than 26h (p75) — that slow quarter is the
cheapest available lever.

**Caveat:** won-only view. A source can look fast because its slow leads die rather
than close. Pair with a lost-deal pull before spend decisions.

## Log

- 2026-08-04 — Missed-call analysis for Pourya (findings in
  [[2026-08-04-pourya-missed-calls]]). Two corrections surfaced, both applied
  above on Albert's instruction: (1) the ID table's `assignedUserId` example
  `rAMFCiXbAjJOEjtyyvmn` was labelled Albert — it is **Pourya Lalee**; Albert is
  `ooPNab06Ka04uZ1yQ4w6`. Full user map recorded from `/users/`: Front Desk
  `edv6p75Y79cYsPS0jPv0`, Mark Bot `CvW3gPWmxP0OkyUiFmhT`, Michael Tran
  `GH0XAA6gD38CEMR9oREm`; Pourya's direct line +16476060295. (2) Reverse of the
  2026-07-26 token trap: this session's *process env* held a stale
  `GHL_PIT_TOKEN` (401 on every call) while `.env` had the working one —
  auto-sourcing at shell startup pins the token at launch time, so a rotated
  token needs a fresh shell or an explicit `source .env` before analysis runs.
- 2026-07-26 — `ghl-ingest` run at 00:25 succeeded (307 open opportunities; 4 new leads;
  full report). A follow-up run at 20:05 failed 401 "Invalid JWT" on every call because
  `GHL_PIT_TOKEN`/`GHL_LOCATION_ID` were absent from that session's process environment
  (`.mcp.json` only reads process env, doesn't load `.env` itself) — per the ingest
  contract's idempotent-overwrite rule, the error record replaced the good 00:25 output
  in `ingest/2026-07-26/ghl.json`. Fixed on this machine by auto-sourcing `.env` from
  shell startup so the token is always present before `claude` launches. **New trap:**
  a missing/expired token doesn't fail loudly — it silently produces a same-shaped
  `status: "error"` ingest file that overwrites good data, so check `status` before
  trusting a "successful" ingest run.
  Also surfaced: the 00:25 run found live auto-abandonment firing at ~14d (New Lead)
  and ~40d (Meeting) — earlier than the 28d/60d documented in the table above and in
  `config/ghl-workflow.json`. Unconfirmed whether the live GHL workflow changed or the
  config/table is stale — needs verification directly against GHL, not corrected here.
- 2026-07-25 (later still) — Reworded the percentile findings in plain English at
  Albert's request (p90/p75 read as "1 in 10" / "1 in 4" rather than bare notation) and
  added a "Reading the percentiles" decoder above the win-timeline section. Numbers and
  conclusions unchanged — wording only. Note this edited prose above the `## Log`, which
  `CONVENTIONS.md` rule 2 otherwise reserves to Albert; done on his explicit instruction.
- 2026-07-25 (later) — Ran the v2 workflow-aware `ghl-ingest`: 30 items, 70 drift
  findings (22 categorization misses, 15 untagged in call queue, 12 actionable
  stale-approaching). Measured the Meeting-scheduled window for the first time
  (above). Recorded per-stage stale thresholds and the full ID reference. Also
  backfilled `ghl_contact_id` into every client note — the vault previously linked
  to GHL by name only, so a rename in GHL would have created duplicate notes.
- 2026-07-25 — Wired GHL MCP (read-only PIT). Ran first `ghl-ingest`. Completed
  win-timeline + activity analysis over all 297 won opportunities; findings above.
- 2026-07-24 — `ghl-ingest` (standalone run): 4 new leads, 18 unanswered conversations,
  2 pipeline moves. New quirk observed: vendor/supplier solicitations arrive in the
  *lead* stream as ordinary contacts (e.g. a WhatsApp cash offer logged as "Omega
  Distributors"), so raw lead counts overstate retail demand. Also ~1/3 of the
  unanswered queue is missed calls with no voicemail and automated "We've Moved" log
  entries — the unanswered-conversation metric needs those filtered before it means
  anything. Day recorded in [[2026-07-24]].
