---
type: opportunity
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: dormant
last_activity: 2026-09-19
# Source-system IDs — the join keys. Names are display; IDs are identity.
# ghl_pipeline/stage are names, not IDs: stage IDs are opaque and get renamed in
# the GHL UI, so the name is what a human can verify. The opportunity ID is the anchor.
ghl_opportunity_id: yFW2NB5WWfRhpd5JCIdT
ghl_contact_id: IwxPuw1IDDifSpReVNA9
ghl_pipeline: (1) PROJECT: Lead Qualification
ghl_stage: 0c. ASAP (Hot)
# Operational, not identity: who owns this record in GHL right now (name + id).
ghl_assigned_to: Front Desk at Titan Flooring Inc.
ghl_assigned_to_id: edv6p75Y79cYsPS0jPv0
---

# Muhammad Rafiq

**Client:** [[Muhammad Rafiq]]
**Scope:** Stairs — vinyl treads
**Value:** $1,950.00 CAD
**Links:** —

## Context
<!-- human-owned -->

## Log
- 2026-09-07 — created from GHL daily ingest, top-level `needs_attention`: mobile quote sent for a stairs job (vinyl treads); customer replied "No thanks" to our follow-up yesterday — a clear decline. Still tagged `lead: hot` and sitting in `0c. ASAP (Hot)` (3.7 days, 53% of the 7-day threshold) — tag doesn't match the outcome; needs correcting to cold/unqualified. See [[Muhammad Rafiq]] Log.
- 2026-09-19 — GHL daily ingest, top-level `needs_attention`: opportunity auto-abandoned today (14 days in `0c. ASAP (Hot)`, 200% of the 7-day threshold) — still tagged `lead: hot` at abandonment, and automated nurture (text + YouTube link) kept messaging him through Sep 18 despite his "No thanks" decline on Sep 6. Tag/automation hygiene issue, not a reopened deal. See [[Muhammad Rafiq]] client Log.
