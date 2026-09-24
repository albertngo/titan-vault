---
type: opportunity
visibility: staff
status: active
last_activity: 2026-09-24
# Source-system IDs — the join keys. Names are display; IDs are identity.
ghl_opportunity_id: plDAaaMcaOhZYIsIpyC4
ghl_assigned_to: Pourya Lalee
ghl_assigned_to_id: rAMFCiXbAjJOEjtyyvmn
ghl_contact_id: LhXVwRvJY4ExDCcWZJW3
ghl_pipeline: (2) PROJECT: Sales Pipeline
ghl_stage: *Meeting (Scheduled)* CCAM|GHL
---

# Maria - Waterdown

**Client:** [[Maria Wildfang]]
**Scope:**
**Value:** $41,150 CAD
**Links:**

## Context
<!-- human-owned -->

## Log
- 2026-07-26 — created from GHL 2-month pull (opportunities created 2026-05-26 → 2026-07-26). Created in GHL 2026-06-16; stage "*Meeting (Scheduled)* CCAM|GHL"; status open; value $41,150 CAD; source onlineMeta Ad; contact tags: meta-ad-squeeky, lead: warm, appt-home, mobile quote.
- 2026-07-28 — GHL daily ingest drift (`meeting_no_followup`, high): 38 days since the Jun 20 in-home visit with zero outbound; 42 days in stage vs the 30-day threshold, no `stale_lead` tag. Largest open deal in the account — today's brief calls for a manual touch (no sequence covers this stage).
- 2026-08-31 — GHL daily ingest, top-level `needs_attention` (~$83K Meeting-scheduled group) + drift `stale_approaching` (253% of threshold, high): 75.9 days in Meeting (Scheduled) vs the 30-day threshold, still no `stale_lead` tag. Largest single opportunity in the group.
- 2026-09-01 — GHL daily ingest, top-level `needs_attention` + drift `stale_approaching` (256% of threshold, high): 76.9 days in stage. Pourya flagged this internally today as "too high value not to probe" but no outbound has actually gone to the customer since Jul 24 — still the largest single open opportunity in the account.
- 2026-09-02 — GHL daily ingest, top-level `needs_attention` + drift `stale_approaching` (260% of threshold, high): a reconnect call happened yesterday but the outcome isn't logged — 77.9 days in Meeting (Scheduled). See [[Maria Wildfang]] Log for detail.
- 2026-09-03 — GHL daily ingest, top-level `needs_attention` + drift `meeting_no_followup` (high, 263% of the 30-day threshold, 48.9 days overdue): 78.9 days in Meeting (Scheduled), 74.9 days since the in-home visit — past the 60-day auto-abandon point, still no `stale_lead` tag, automation not wired to this stage. See [[Maria Wildfang]] Log for detail.
- 2026-09-04 — GHL daily ingest, top-level `needs_attention` + drift `stale_approaching` (high, 266% of the 30-day threshold, 49.9 days overdue): 79.9 days in Meeting (Scheduled), still no `stale_lead` tag. See [[Maria Wildfang]] Log for detail.
- 2026-09-06 — GHL daily ingest, top-level `needs_attention` (item 4) + drift `meeting_no_followup` (high, 273% of the 30-day threshold, effective_window_days=26): 81.9 days in Meeting (Scheduled), still no `stale_lead` tag. See [[Maria Wildfang]] Log for detail.
- 2026-09-11 — GHL daily ingest, `By source` detail (drift `meeting_no_followup`, high): 83 days since the in-home visit, zero follow-up — today's single largest drift miss (of 30 findings). See [[Maria Wildfang]] Log.
- 2026-09-17 — GHL daily ingest, top-level `needs_attention` (item 4, high) + drift `meeting_no_followup`: 92.9 days in Meeting (Scheduled), 310% of the 30-day threshold — highest-value stalled deal in the pipeline. Pourya's Aug 31 "a goner" risk note reiterated in today's brief. See [[Maria Wildfang]] Log.
- 2026-09-24 — GHL daily ingest, top-level `needs_attention` (item 5, named individually as worst of 8 past-150%-threshold opportunities) + drift `stale_approaching` (high, 333% of the 30-day threshold): now 100 days in Meeting (Scheduled), still no `stale_lead` tag, last outbound touch Sep 1. Still no follow-up sequence exists for this stage — directly relevant to the sequence Albert is designing. See [[Maria Wildfang]] Log.
