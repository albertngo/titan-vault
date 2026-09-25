---
type: opportunity
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: dormant
last_activity: 2026-09-25
# Source-system IDs — the join keys. Names are display; IDs are identity.
# ghl_pipeline/stage are names, not IDs: stage IDs are opaque and get renamed in
# the GHL UI, so the name is what a human can verify. The opportunity ID is the anchor.
ghl_opportunity_id: NhPcR8AT7Wdda5UC2YNl
ghl_contact_id: Zqf3dAjXvxqvNucUVMrw
ghl_pipeline: (1) PROJECT: Lead Qualification
ghl_stage: 0a. New Lead
# Operational, not identity: who owns this record in GHL right now (name + id).
ghl_assigned_to:
ghl_assigned_to_id:
---

# Manjinder Athwal - Flooring - Caledon

**Client:** [[Manjinder Athwal]]
**Scope:** (not specified in today's ingest)
**Value:** (not provided — `value_cents` null in today's pull)
**Links:** —

## Context
<!-- human-owned -->

## Log
- 2026-09-25 — created from GHL daily ingest, top-level `needs_attention` (item 4, priority high) + `stragglers_ranked` rank 4: auto-abandoned today at only 7.04 days in `0a. New Lead` (50.3% of this run's own 14-day stale threshold for that stage) — well short of the 28-day threshold documented elsewhere, so the auto-abandon appears to be running on a faster/different cadence than expected. Carries the `ai_qualify` tag; an AI voicemail-calling sequence tried him 4x in Oct-Nov 2025 on an earlier inquiry and never connected. Worth confirming with Albert whether `ai_qualify` runs its own undocumented cadence. See [[Manjinder Athwal]] Log.
