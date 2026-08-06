---
type: opportunity
visibility: staff
status: active
last_activity: 2026-08-06
# Source-system IDs — the join keys. Names are display; IDs are identity.
# ghl_pipeline/stage are names, not IDs: stage IDs are opaque and get renamed in
# the GHL UI, so the name is what a human can verify. The opportunity ID is the anchor.
ghl_opportunity_id: u22LpsKH96O0TNLEefk3
ghl_contact_id: 4ZNPHGPIJDd740pSfPzX
ghl_pipeline: (2) PROJECT: Sales Pipeline
ghl_stage: *Meeting (Scheduled)* CCAM|GHL
# Operational, not identity: who owns this record in GHL right now (name + id).
ghl_assigned_to:
ghl_assigned_to_id:
---

# Jonathan Spence

**Client:** [[Jonathan Spence]]
**Scope:** (not provided in today's ingest)
**Value:** $0 CAD (per GHL; opportunity value not set)
**Links:**

## Context
<!-- human-owned -->

## Log
- 2026-08-06 — created from GHL daily ingest `needs_attention` (anomaly): opportunity `status` has read `abandoned` since 2026-06-15 and was never reopened, but today's in-home-visit reschedule (to 2026-08-07 10:00am) moved the stage to *Meeting (Scheduled)* — GHL is now tracking a live confirmed appointment on a formally closed-out opportunity. Needs the status reopened to match the live stage, or the appointment reconciled against the abandonment.
