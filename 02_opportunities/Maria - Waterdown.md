---
type: opportunity
visibility: staff
status: active
last_activity: 2026-09-03
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
- 2026-09-02 — GHL daily ingest, top-level `needs_attention` + drift `stale_approaching` (260% of threshold, high): a reconnect call happened yesterday but the outcome isn't logged; 77.9 days in Meeting (Scheduled). See [[Maria Wildfang]] Log for detail.
- 2026-09-03 — GHL daily ingest, top-level `needs_attention` + drift `meeting_no_followup` (high, 263% of the 30-day threshold, 48.9 days overdue): 78.9 days in Meeting (Scheduled), 74.9 days since the in-home visit — past the 60-day auto-abandon point, still no `stale_lead` tag, automation not wired to this stage. See [[Maria Wildfang]] Log for detail.
