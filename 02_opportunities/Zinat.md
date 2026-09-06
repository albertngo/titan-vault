---
type: opportunity
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: dormant
last_activity: 2026-09-06
# Source-system IDs — the join keys. Names are display; IDs are identity.
# ghl_pipeline/stage are names, not IDs: stage IDs are opaque and get renamed in
# the GHL UI, so the name is what a human can verify. The opportunity ID is the anchor.
ghl_opportunity_id: anydILbkxw8CMoVAGRZC
ghl_contact_id: oAEmYcwTQXperRXa7HR1
ghl_pipeline: (2) PROJECT: Sales Pipeline
ghl_stage: 1b. Postponed
# Operational, not identity: who owns this record in GHL right now (name + id).
ghl_assigned_to: Pourya Lalee
ghl_assigned_to_id: rAMFCiXbAjJOEjtyyvmn
---

# Zinat

**Client:** [[Zinat]]
**Scope:** (not provided in today's ingest)
**Value:** $14,000 CAD
**Links:** —

## Context
<!-- human-owned -->

## Log
- 2026-09-06 — created from GHL daily ingest, top-level `needs_attention` (item 5, `stragglers_ranked` rank 7) + drift `abandonment_next` (high): 267.9 days in `1b. Postponed` — 88 days past the 180-day (2×90) abandon-equivalent point for this stage. `stale_lead` is applied but the opportunity never auto-abandoned; worth checking whether the automation is stuck on this specific record. Checked the vault by ID (`anydILbkxw8CMoVAGRZC` / contact `oAEmYcwTQXperRXa7HR1`) and name first — no existing match.
