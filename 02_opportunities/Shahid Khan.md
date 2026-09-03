---
type: opportunity
visibility: staff
status: active
last_activity: 2026-09-03
# Source-system IDs — the join keys. Names are display; IDs are identity.
# ghl_pipeline/stage are names, not IDs: stage IDs are opaque and get renamed in
# the GHL UI, so the name is what a human can verify. The opportunity ID is the anchor.
ghl_opportunity_id: 8lVbE6kXysWuEj2gEbMY
ghl_contact_id: TAPx6WmRYKKV9zHk7Q1Y
ghl_pipeline: (2) PROJECT: Sales Pipeline
ghl_stage: *Meeting (Scheduled)* CCAM|GHL
# Operational, not identity: who owns this record in GHL right now (name + id).
ghl_assigned_to: Pourya Lalee
ghl_assigned_to_id: rAMFCiXbAjJOEjtyyvmn
---

# Shahid Khan

**Client:** [[Shahid Khan]]
**Scope:** (not provided in today's ingest)
**Value:** $10,385.00 CAD
**Links:**

## Context
<!-- human-owned -->
Possible duplicate-opportunity split: the same contact (`TAPx6WmRYKKV9zHk7Q1Y`) also carries opportunity `10zuagZJvDpALlRC8Vqn` (pipeline "(1) PROJECT: Lead Qualification", stage "0b. Later Date (Warm)", $0 value), which GHL auto-abandoned 2026-09-03. Not merged — see [[Shahid Khan]] (client) Log.

## Log
- 2026-09-03 — created from GHL daily ingest, top-level `needs_attention` (high) + drift `meeting_no_followup`: confirmed in-home visit happened 56.0 days ago — just past the 60-day auto-abandon point, no `stale_lead` tag, automation not wired to this pipeline stage. See [[Shahid Khan]] (client) Log for detail.
