---
type: platform
status: active
last_activity: 2026-07-25
---

# GHL (GoHighLevel)

Titan's CRM: lead capture, call routing, SMS/email conversations and automation,
sales pipelines, mobile quotes. Source of truth for lead flow and deal stage.
Read by `ghl-ingest` (read-only, daily); written only by `ghl-actions`
(write, approval-gated). Both live in titan-agents.

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

## Lead qualification workflow (current)

1. Lead comes in → enters the leads pipeline.
2. **Call queue:** within 5 minutes GHL rings Albert; if he picks up, it rings the
   customer. The lead stays in the call queue until Albert categorizes and tags them.
3. **Missed call** → automatic SMS goes out. Albert works the tagged call-queue list
   afterward.
4. Regardless of contact, the lead enters **general nurture** (email marketing) and
   sits there until categorization.
5. On direct contact (call or SMS), the lead is moved and tagged:
   `hot` / `warm` / `cold` / `unqualified`.
6. **Mobile quote is the tagging trigger.** Albert fills the mobile quote form during
   or after the conversation; the timeline field he enters determines the tag. When the
   quote sends via automation, the contact is tagged and moved to the matching stage.
7. **+5 days after quote:** automated follow-up text asking what they thought.
8. After that, no more push.

### Stale workflow

- Too long in a stage → one automated follow-up.
- Set days after that follow-up → contact tagged `stale lead` (candidate for manual
  follow-up).
- Same duration passes again with the stale tag already present → automatically marked
  `abandoned`.

### Sales pipeline & appointments

Stages: Meeting scheduled → Postponed → Projects won.
Appointments live in **Meeting scheduled** with three occurrence types:

- In-home visit
- In-store visit
- Both (tagged for both if they book both)

> ⚠️ **Known gap:** no follow-up sequence exists for Meeting scheduled — these contacts
> have taken direct physical action but get no structured push. Being designed from real
> data via the `/won-analysis` command in titan-agents (source, days lead→contact, days
> lead→appointment, days appointment→won, contact points, conversation quality).

## Tag vocabulary (canonical)

`hot` · `warm` · `cold` · `unqualified` · `stale lead` · `abandoned` · untagged
(in call queue / nurture, not yet categorized)

Tags are **ground truth** — set only by Albert (via mobile quote timeline) or by the
stale automation. Agents read them, never write them. Agent-detected mismatches between
conversation content and tag surface in the daily brief as `tag_mismatch`, for Albert to
resolve.

## Contact IDs (vault join key)

The GHL contact UUID is the canonical identifier for a client across the vault — see
rule 5 in `CONVENTIONS.md`. It lives in `ghl_contact_id` in client frontmatter and is
stable across contact renames, which names are not.

Deep link pattern (location `4BwjVRlyDCR4ZRdcSrFR`):

```
https://app.gohighlevel.com/v2/location/4BwjVRlyDCR4ZRdcSrFR/contacts/detail/<ghl_contact_id>
```

> ⚠️ Pattern written from the GHL v2 URL shape, **not yet verified** against a live
> contact — confirm once and correct here if the path differs.

## Quirks worth knowing

- `lastStatusChangeAt` is the real close timestamp; `updatedAt` drifts with any edit.
- Source values arrive unnormalized — `Store` and `store` are the same channel.
- Contact records often predate their opportunity by months (repeat customers), so
  "lead age" ≠ sales-cycle length. Use opportunity `createdAt` for cycle time.
- Appointments appear as `TYPE_ACTIVITY_APPOINTMENT` events in the conversation
  stream, not as a separate object. Body prefix `Visit:` = in-home, `Store:` = in-store.
- Only ~1% of logged touches are automated; the funnel is manual today.
- Qualification is manual **by design** — the daily ingest's drift detection exists to
  catch categorization misses, quotes whose 5-day follow-up didn't fire, and
  stale/abandonment approaches.

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

- 2026-07-25 — Documented the lead qualification workflow, stale/abandonment
  automation, appointment types, and canonical tag vocabulary as part of the
  `ghl-ingest` v2 build. Recorded the Meeting-scheduled follow-up gap.
- 2026-07-25 — Wired GHL MCP (read-only PIT). Ran first `ghl-ingest`. Completed
  win-timeline + activity analysis over all 297 won opportunities; findings above.
- 2026-07-24 — `ghl-ingest` (standalone run): 4 new leads, 18 unanswered conversations,
  2 pipeline moves. New quirk observed: vendor/supplier solicitations arrive in the
  *lead* stream as ordinary contacts (e.g. a WhatsApp cash offer logged as "Omega
  Distributors"), so raw lead counts overstate retail demand. Also ~1/3 of the
  unanswered queue is missed calls with no voicemail and automated "We've Moved" log
  entries — the unanswered-conversation metric needs those filtered before it means
  anything. Day recorded in [[2026-07-24]].
