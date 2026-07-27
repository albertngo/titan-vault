---
type: analysis
date: 2026-07-26
question: How long does a win take from lead → appointment → won, what does it cost in touches, and when is it too early to abandon a lead?
sources: [GHL, "titan-agents: ingest/analysis/won-analysis-2026-07-26.md", "titan-agents: ingest/analysis/won-records.json", "titan-agents: analysis/output/won_rows.csv + stats.json"]
---

# Won analysis — all 297 historical wins

**Question:** How long from lead to appointment to won, with how many touch points
across which channels — and where should abandonment thresholds sit, per stage and
source?

**Answer:** Project wins (n=290, $2.38M) close in a median **13.9-day cycle** (p75
31 d) on a median **37 touches**, 76% of them SMS and 98% manual. The appointment
books almost immediately (median 0.9 d after the lead) but the close comes **~16
days after the appointment** (p75 **42 d**), with a median of **30 more touches**
in between — that post-appointment stretch is the window the Meeting-scheduled
sequence must cover. Thresholds are source-dependent: Store wins finish by ~4 weeks
(p75 28.5 d) but **Meta Ad wins take up to 7 weeks** (p75 51 d), so one global
abandonment timer — like the 7-day hot threshold that killed [[Bushra Masoom]]'s
$29,690 opportunity today — is too aggressive for ad leads. Store material wins
(n=6) are a separate, tiny population and were never averaged in.

## Findings

| Timeline segment (PROJECT wins) | Median | p75 |
|---|---|---|
| Deal cycle (opp created → won) | 13.9 d | 31.0 d |
| Lead → appointment (n=175) | 0.9 d | 6.6 d |
| **Appointment → won** (n=175) | **16.0 d** | **42.1 d** |
| Touches before appointment | 4 | 12 |
| Touches after appointment | **30** | 51 |
| First response to first inbound | 103 min | 25.5 h |

- By source: Store 197 wins / $1.58M / cycle 12.8–28.5 d / 35 touches; **Meta Ad 60
  wins / $491K / cycle 20–51 d / 54.5 touches / 83% appointment rate**. Long tail
  (12 labels, 16 wins) excluded; source labels are drifting (`Store` vs `store`,
  `onlinePreliminary Mobile Quote`) since 2026-06.
- **Store visit = bigger deals:** in-home + in-store wins average $10.9K vs $7.4K
  for in-home only, and close tighter (p75 22 d vs 50 d). 40% of wins ($861K) had
  no appointment at all.
- Channel mix: SMS 76%, calls 19%, email 4.5%. Outbound:inbound 1.19:1. Automated
  share just 2%.
- Evidence-backed abandonment floors: Store leads ≥30 d, Meta Ad leads ≥50 d,
  Meeting-stage deals ≥45 d post-appointment. (Won-only view — these are "too early
  to kill" floors, not conversion odds; ~1,132 abandoned opps are the unmeasured
  denominator.)
- Recommended Meeting-scheduled cadence (day offsets post-appointment):
  0 SMS · 2 call · 5 SMS · 9 call+SMS store-visit invite · 16 SMS · 23 SMS ·
  30 call · 42 final call + close-out SMS · then stale/Postponed. Copy and
  automation split still need Albert's judgment — see the full report.
- Anomaly: one $0 "won" record (Elena Pass) misfiled in the Lead Qualification
  pipeline — fix manually in [[GHL]].

## Related

Wins with vault notes (17 of 297 — the rest closed before vault coverage begins
2026-05-26): [[Gustavo - Oakville]] ([[Gustavo Galvis]]), [[Jason - Oakville]]
([[Jason Law]]), [[Stephen - Whitby]], [[Helen - Mississauga]],
[[Syed And Azara - Milton]] ([[Syed and Azara Shah]]), [[Sean]],
[[King - BRAMPTON]] ([[King Chan]]), [[Phinkham Laungeraj - Brampton]]
([[Phinkham Laungeraj]]), [[Arkadi - Thornhill]] ([[Arkadi Chmir]]),
[[Orlando - Mississauga]], [[Sajeda - Stoney Creek]] ([[Sajeda Munshi]]),
[[Daria - Mississauga]] ([[Daria]]), [[Daniella - Mississauga]]
([[Daniella Powel]]), [[Ashrim - Milton]], [[David - Ancaster]]
([[David Rooney]]), [[Glendy - Mississauga]], [[SALIH - Cambridge]].
Also cited: [[Bushra Masoom]] (open, abandonment case study).

## Source data

Raw corpus in titan-agents (system of record): full report at
`ingest/analysis/won-analysis-2026-07-26.md`, per-win records at
`ingest/analysis/won-records.json`, row data at `analysis/output/won_rows.csv`,
aggregates at `analysis/output/stats.json` (commit `58279d2`). Method:
`methods/ghl-analysis-framework.md`. Appointment modes classified by event-body
prefix, which can disagree with the `appt-home`/`appt-store` tags the daily
ingester reads.
