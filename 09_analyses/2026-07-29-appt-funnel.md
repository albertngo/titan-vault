---
type: analysis
date: 2026-07-29
question: Is opp→appointment really ~0 days, or an artifact of deleted/recreated opportunities — and what does the appointment funnel look like over ALL opportunities, not just wins?
sources: [GHL, "titan-agents: analysis/output/appt_funnel_rows.csv + appt_funnel_stats.json", "titan-agents: methods/appt-funnel.md"]
---

# Appointment funnel — all 1,961 opportunities

**Question:** Albert challenged the won-analysis finding that appointments book
~0 days after opportunity creation: the ad-lead flow (nurture SMS → answered
call → booking days later) should take longer, and maybe opportunities get
deleted from the Leads pipeline and recreated in the sales pipeline at booking,
resetting `createdAt`. Test both against the full opportunity list — including
the much bigger pool that booked an appointment but never won.

**Answer:** The ~0 is real. Booking speed from opportunity creation is
near-zero across **every** outcome (won 0.0/0.8 d median/p75, lost 0.0/0.8,
abandoned 0.0/1.2, open 0.0/0.8) — a funnel property, not won-only bias. The
delete-recreate hypothesis is dead: deletions are logged in conversation
histories, only 7 of 297 wins (2.4%) have a `createdAt` right after one, and
Meta Ad opportunities are created *together with the contact* at lead arrival.
The real pattern is **bimodal: leads either book almost immediately or never
book.** The nurture path exists but is the minority — of 256 Meta Ad bookings,
only 18% took more than a week from contact creation; 991 Meta Ad
opportunities were abandoned with only 13% ever booking. Appointment leverage,
finally with the true denominator: closed deals that booked won **39% vs 11%**
for those that never booked (3.5×).

## Findings

| Status | n | Booked | Opp→booking med/p75 | Contact→booking med/p75 |
|---|---|---|---|---|
| Won | 298 | 55% | 0.0 / 0.8 d | 0.9 / 7.0 d |
| Lost | 223 | 31% | 0.0 / 0.8 d | 0.3 / 2.8 d |
| Abandoned | 1,137 | 17% | 0.0 / 1.2 d | 0.8 / 4.0 d |
| Open | 303 | 20% | 0.0 / 0.8 d | 0.4 / 6.6 d |

- **Booked-but-didn't-win pool: 260** (190 abandoned + 70 lost) vs 165 booked
  wins — Albert's guess that this pool is bigger was right.
- Booked deals that abandoned took median 45 d (p75 79) to be marked
  abandoned; the ~31 d post-appointment follow-up window from
  [[2026-07-26-won-analysis]] covers most of the winnable stretch first.
- Scheduled visit sits a median ~2 d after booking (booking `dateAdded` vs
  calendar `startTime`); conversation appointment events fire at **booking**
  time (84% within 2 h), so both analyses share one clock.
- Opportunity deletion exists as a rare manual habit: 39 deletion events in
  the won corpus, only 9 followed by a re-creation within 7 d. Deleted-opp
  pipeline/stage is recoverable from the conversation activity events.
- Store vs Meta Ad: Store books at the visit itself (median and p75 ≈ 0);
  Meta Ad wins book median 0.8 d / p75 2.8 d after opp creation. Store
  abandoned (n=78) books at 59% — walk-ins that booked and still died.
- Caveat: appointment rates are floors — calendars cover 89% of the won
  corpus's known appointments; misses skew to store walk-ins logged only in
  conversations. Timing comparisons are unaffected.

## Related

[[2026-07-26-won-analysis]] (won-only view this corrects and extends),
[[GHL]] (platform), [[Bushra Masoom]] (the abandonment case that motivated
follow-up-window work).

## Source data

Raw corpus in titan-agents (system of record): rows at
`analysis/output/appt_funnel_rows.csv`, aggregates at
`analysis/output/appt_funnel_stats.json`. Method: `methods/appt-funnel.md`
(calendar-events source, deal-window join, coverage validation) — shared
definitions in `methods/ghl-analysis-framework.md` v2. Appointments from the
calendars API; booking moment = event `dateAdded`.
