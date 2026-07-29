---
type: decision
status: decided
date: 2026-07-28
---

# Booked-appointment leads: follow-up cue at 30 days, close-out at 40

**Decision (Albert + Pourya, project-status meeting 2026-07-28):** for
opportunities that booked an appointment, fire the first follow-up cue at
**30 days** post-appointment, tiered by job value — roughly $20K+ gets a
personal phone call plus a follow-up message (tracked as a task); smaller jobs
get automated follow-ups. At **40 days** the lead is closed out/abandoned
unless the client signals they're still in market, which extends it. Pourya
chose 40 over Albert's 40–50 range: "If we're gonna do the 40 days, we can do
the 40 and see how it pans out" — explicitly a trial setting.

**Evidence presented live:** Albert's pull of the 176 most recent
booked-appointment projects — median appointment→close **16 days**, 25% within
**8 days**, 75% within **42 days**; beyond 42 mostly outliers/losses. This is
an appointment→close cut done in GHL for the meeting; the vault's
[[2026-07-29-appt-funnel]] (opp→booking over all 1,961 opportunities: bimodal
book-fast-or-never; booked-then-abandoned deals die at median 45 d) and
[[2026-07-26-won-analysis]] (~31 d winnable post-appointment window) point the
same direction from different angles.

**Context:** extends the 2026-07-21 stale-lead policy (30-day abandon <$20K /
postpone >$20K / drop insurance leads) with hard timing data. Implementation —
the GHL workflow build (30-day cue, value-tier branch, 40-day auto close-out
with still-in-market extension) — has no live home yet: the SALES FOLLOWUP CII
in [[Notion]] is marked Done, and a new Funnel/Sales CII was suggested on the
Jul 28 meeting summary but not yet created. Fourth consecutive meeting touching
stale-lead flow.
