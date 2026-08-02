---
type: opportunity
visibility: staff
status: active
last_activity: 2026-07-28
# Source-system IDs — the join keys. Names are display; IDs are identity.
ghl_opportunity_id: 4gPXisJKRMHGxdAwCNZL
ghl_assigned_to: Pourya Lalee
ghl_assigned_to_id: rAMFCiXbAjJOEjtyyvmn
ghl_contact_id: GByNBlYcqJFQuA20EMdc
ghl_pipeline: (2) PROJECT: Sales Pipeline
ghl_stage: *Meeting (Scheduled)* CCAM|GHL
---

# Silviya - TORONTO

**Client:** [[Silviya Jardany]]
**Scope:**
**Value:** $6,500 CAD
**Links:**

## Context
<!-- human-owned -->

## Log
- 2026-07-26 — created from GHL 2-month pull (opportunities created 2026-05-26 → 2026-07-26). Created in GHL 2026-06-20; stage "*Meeting (Scheduled)* CCAM|GHL"; status open; value $6,500 CAD; source Store; contact tags: ccam, appt-home, appt-store.
- 2026-07-28 — GHL daily ingest drift (`meeting_no_followup`, high): appointment is TOMORROW (Jul 29 4:00pm, booked Jul 25; GHL appt `A99Bt73Yav9Rs7r0RKmD`) but the stage clock is at 37.9d vs the 30-day threshold — effective follow-up window −9 days, so stale fires before any post-visit follow-up is possible. The meeting-window config bug, now observable live.
