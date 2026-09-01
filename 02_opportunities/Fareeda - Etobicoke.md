---
type: opportunity
visibility: staff
status: dormant
last_activity: 2026-09-01
# Source-system IDs — the join keys. Names are display; IDs are identity.
ghl_opportunity_id: lNrXKin7I6CVLp060lnu
ghl_assigned_to: Pourya Lalee
ghl_assigned_to_id: rAMFCiXbAjJOEjtyyvmn
ghl_contact_id: kQxiUK8760N7We26mBS0
ghl_pipeline: (2) PROJECT: Sales Pipeline
ghl_stage: *Meeting (Scheduled)* CCAM|GHL
---

# Fareeda - Etobicoke

**Client:** [[Fareeda Chand]]
**Scope:**
**Value:** $14,690 CAD
**Links:**

## Context
<!-- human-owned -->

## Log
- 2026-07-26 — created from GHL 2-month pull (opportunities created 2026-05-26 → 2026-07-26). Created in GHL 2026-06-17; stage "*Meeting (Scheduled)* CCAM|GHL"; status open; value $14,690 CAD; source onlinePreliminary Mobile Quote; contact tags: mobile quote, lead: cold, appt-home.
- 2026-08-31 — GHL daily ingest, top-level `needs_attention` (~$83K Meeting-scheduled group) + drift `meeting_no_followup` (high): 67 days since the Jun 25 in-home visit with zero outbound contact; 71.7 days in Meeting (Scheduled), 239% of the 30-day threshold, still tagged `lead: cold`. Client note [[Fareeda Chand]] created this run — was a dangling link before.
- 2026-09-01 — GHL daily ingest, top-level `needs_attention` (conversation `mf49MwVOP184GfJeH5UB`): explicit decline today after 67 days of silence — she has decided not to proceed. Still shown open in Meeting-scheduled in GHL; should be moved/closed as lost. `status` set to `dormant` here pending that GHL close-out.
