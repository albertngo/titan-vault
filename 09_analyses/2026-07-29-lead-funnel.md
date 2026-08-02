---
type: analysis
visibility: admin
date: 2026-07-29
question: What does the last 60 days of lead flow look like — trend, appointment booking by source, daily mix?
sources: [GHL, "titan-agents: analysis/output/lead_rows.csv", "titan-agents: analysis/output/lead_stats.json"]
---

# Lead funnel — 60 days to 2026-07-28

**Question:** What is the lead trend, which sources actually book appointments, and what does the daily source mix look like?
**Answer:** Volume is softening — the 7-day average slid from ~5.5 leads/day in early June to ~2.5 by late July. Meta Ads supplies two-thirds of all leads (151 of 226) but books appointments at only 15%, while Mobile Quote requests book at 75% — the strongest signal in the data is that a lead who asks for a mobile quote is a different animal from a raw Meta form fill and deserves a different follow-up track. Google produced 8 leads and zero booked appointments ($86K quoted value at 0%). Store/Walk-in converts best end-to-end (18 leads → 5 wins).

## Findings

| Source | Leads | Appts | Appt rate | Won |
|---|---|---|---|---|
| Meta Ads | 151 | 23 | 15% | 3 |
| Other | 25 | 4 | 16% | 1 |
| Store / Walk-in | 18 | 6 | 33% | 5 |
| Mobile Quote | 16 | 12 | **75%** | 3 |
| Google | 8 | 0 | **0%** | 0 |
| Referral | 4 | 2 | 50% | 2 |
| Website | 3 | 3 | 100% | 1 |

- 226 leads in window: 221 project, 5 store-pipeline. 50 booked appointments overall (22%).
- Trend: early-June peak (~5.5/day avg, spike day of 10), late-July trough (~2.5/day) — the last two weeks are the quietest of the window.
- Google's 0/8 is a small sample but carries $86K of quoted value — worth checking what happens to those leads after quote.
- Method traps (full detail in `methods/lead-funnel.md`): GHL carries source in 4 disagreeing places (~20 raw label variants, normalized); appointment has 3 disagreeing signals (per-row provenance kept); daily counts here are opportunities/day, not the ingest's contacts/24h — cross-check direction only.

## Related

[[GHL]] — platform quirks. Individual opportunities not linked: this is an
aggregate analysis; no single entity earned a note by it (earned-relevance
rule).

## Source data

titan-agents repo, PR #4: `analysis/lead_funnel.py` (method+pull),
`analysis/output/lead_rows.csv` + `lead_stats.json` + `chart*.png` (derived,
committed), cache local-only. Re-run: `analysis/lead_funnel.py [--refresh]`.
