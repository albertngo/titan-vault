---
type: opportunity
visibility: staff
status: dormant
last_activity: 2026-09-02
# Source-system IDs — the join keys. Names are display; IDs are identity.
ghl_opportunity_id: 6kgrmLti15NTv8bliraP
ghl_assigned_to: Pourya Lalee
ghl_assigned_to_id: rAMFCiXbAjJOEjtyyvmn
ghl_contact_id: 9et4LUnHmetxVT1xRep3
ghl_pipeline: (2) PROJECT: Sales Pipeline
ghl_stage: *Meeting (Scheduled)* CCAM|GHL
---

# Biplab - Brampton

**Client:** [[Biplab Ghosh]]
**Scope:**
**Value:** $5,182 CAD
**Links:**

## Context
<!-- human-owned -->

## Log
- 2026-07-26 — created from GHL 2-month pull (opportunities created 2026-05-26 → 2026-07-26). Created in GHL 2026-06-30; stage "*Meeting (Scheduled)* CCAM|GHL"; status open; value $5,182 CAD; source onlinePreliminary Mobile Quote; contact tags: mobile quote, lead: warm, appt-cancelled.
- 2026-07-27 — GHL daily ingest drift finding: approaching stale, 27 days in Meeting stage (90% of 30-day threshold, 3 days runway), appt-cancelled with no rebooking/follow-up visible.
- 2026-08-31 — GHL daily ingest drift (`meeting_no_followup`, high; by-source detail only, not today's top-level curated `needs_attention`): 61.9 days in stage, no follow-up since the cancelled appointment 54 days ago, no exit path visible. Light append only.
- 2026-09-02 — GHL daily ingest `pipeline`: moved into "0b. Far Out (Cold)" today, carrying an appt-cancelled tag — the previously booked visit fell through and the lead was pushed back to long-term nurture. `status` set to `dormant` here (was `active`).
