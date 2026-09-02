---
type: opportunity
visibility: staff
status: complete
last_activity: 2026-09-02
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
**Value:** $3,980.00 CAD (won 2026-09-01)
**Links:** https://app.notion.com/3ce596a4505f81d4a72cf4cef06ab439

## Context
<!-- human-owned -->

## Log
- 2026-07-26 — created from GHL 2-month pull (opportunities created 2026-05-26 → 2026-07-26). Created in GHL 2026-06-20; stage "*Meeting (Scheduled)* CCAM|GHL"; status open; value $6,500 CAD; source Store; contact tags: ccam, appt-home, appt-store.
- 2026-07-28 — GHL daily ingest drift (`meeting_no_followup`, high): appointment is TOMORROW (Jul 29 4:00pm, booked Jul 25; GHL appt `A99Bt73Yav9Rs7r0RKmD`) but the stage clock is at 37.9d vs the 30-day threshold — effective follow-up window −9 days, so stale fires before any post-visit follow-up is possible. The meeting-window config bug, now observable live.
- 2026-08-31 — GHL daily ingest drift (`stale_approaching`, 239% of threshold, high; by-source detail only, not today's top-level curated `needs_attention`): 71.8 days in Meeting (Scheduled) vs the 30-day threshold, still untagged. Light append only.
- 2026-09-02 — GHL daily ingest `won_records`: **WON $3,980.00 CAD**, closed 2026-09-01 (value revised down from the $6,500 CAD logged at creation). Cross-confirmed by Notion `new_won_project` on this same opportunity ID. `status` set to `complete` here; needs install scheduling. See [[Silviya Jardany]] Log for detail, including a possible Outlook install-date match flagged under Possible duplicates.
