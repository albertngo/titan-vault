---
type: opportunity
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-08-30
# Source-system IDs — the join keys. Names are display; IDs are identity.
# ghl_pipeline/stage are names, not IDs: stage IDs are opaque and get renamed in
# the GHL UI, so the name is what a human can verify. The opportunity ID is the anchor.
ghl_opportunity_id: EJaWXhz6WPOGh6YhC1jN
ghl_contact_id: H1lLMUAGRdzLrfZlsisf
ghl_pipeline: (1) PROJECT: Lead Qualification
ghl_stage: 0b. Later Date (Warm)
# Operational, not identity: who owns this record in GHL right now (name + id).
ghl_assigned_to: Front Desk
ghl_assigned_to_id: edv6p75Y79cYsPS0jPv0
---

# Vimal Narayan

**Client:** [[Vimal Narayan]]
**Scope:** (not provided in today's ingest)
**Value:** $11,427 CAD
**Links:** —

## Context
<!-- human-owned -->

## Log
- 2026-08-30 — created from GHL daily ingest `stragglers_ranked` (rank 3, conversation `8nUuFCchmvobSiI69VNO`, priority high): duplicate open opportunity for a contact who explicitly declined 2026-08-23 ("got a better price elsewhere"). A separate, correctly-lost opportunity for the same contact exists in GHL but isn't captured as its own note here since it needs no action. This record is still tagged `lead: warm` and receiving nurture emails despite the decline — should be marked lost and closed to match.
