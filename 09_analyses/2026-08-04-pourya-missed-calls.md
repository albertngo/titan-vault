---
type: analysis
visibility: admin
date: 2026-08-04
question: How many incoming calls does Pourya miss per week, and how well are the misses responded to?
sources: [GHL, "titan-agents: analysis/output/pourya_missed_calls.csv", "titan-agents: analysis/output/pourya_missed_calls_summary.json"]
---

# Pourya missed calls — 2 months to 2026-08-04

**Question:** How many incoming missed calls does Pourya have weekly, and how many are responded to well?
**Answer:** Pourya's GHL line took 91 inbound calls over the window (2026-06-05 → 2026-08-05) — ~10/week. He answered 53 and missed 37 (~4/week, 41% of inbound), which collapse into 33 distinct missed-call episodes. Follow-up is fast-or-never: 19 of 33 (58%) got an outbound response at a median of **7.5 minutes** (16 of the 19 within an hour; 14 connected callbacks, 5 SMS), another 9 recovered because the caller rang back and connected, and **5 (15%) got no response at all within 72h** — roughly one caller every two weeks reaching permanent silence. The lever is not response speed, it's the dropped tail.

## Findings

| Outcome of a missed-call episode (n=33) | Count | Share |
|---|---|---|
| We responded (callback/SMS, median 7.5 min) | 19 | 58% |
| Caller rang back and connected first | 9 | 27% |
| No response within 72h | 5 | 15% |

- The 5 unresponded: Christopher (Sat 06-27), Ashrim Narsinh (Sat 07-04), two unnamed contacts (07-08, 07-14 evening), Peter Brick (07-15 — left a voicemail, never returned).
- Patterns in the misses: 12–1pm is the biggest window (10 of 33 episodes); Wed and Sat are the heaviest days; 2 of the 5 dropped ones were Saturdays.
- Trend: miss rate spiked the week of Jun 29 (8 of 11 calls missed) and settled to 2–3 misses/week from mid-July.
- Caveats: GHL line only (personal-cell calls and walk-ins invisible); "responded" counts any outbound touch by anyone at Titan; a call belongs to Pourya via message `userId` or `to` = his direct line +16476060295.

## Related

[[GHL]] — platform quirks; user-ID correction recorded there this date.
Individual contacts not linked: aggregate analysis, no single entity earned a
note by it (earned-relevance rule). The 5 unresponded contacts are named in
the CSV if follow-up is wanted.

## Source data

titan-agents repo: `analysis/pourya_missed_calls.py` (method+pull, cached),
`analysis/output/pourya_missed_calls.csv` (one row per episode) +
`pourya_missed_calls_summary.json`. Method traps in
`methods/missed-call-response.md`.
