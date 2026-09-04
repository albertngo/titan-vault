---
type: opportunity
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-09-04
# Source-system IDs — the join keys. Names are display; IDs are identity.
# ghl_pipeline/stage are names, not IDs: stage IDs are opaque and get renamed in
# the GHL UI, so the name is what a human can verify. The opportunity ID is the anchor.
ghl_opportunity_id: ZJvmCRP4R6zbNV2jMqpX
ghl_contact_id: BpGy2k0bSOHbtzzpsupu
ghl_pipeline: (2) PROJECT: Sales Pipeline
ghl_stage: *Meeting (Scheduled)* CCAM|GHL
# Operational, not identity: who owns this record in GHL right now (name + id).
ghl_assigned_to: Pourya Lalee
ghl_assigned_to_id: rAMFCiXbAjJOEjtyyvmn
---

# Firoz Rajan - Insurance Claim

**Client:** [[Firoz Rajan]]
**Scope:** Insurance-adjuster-approved flooring claim
**Value:** ~$9,000 CAD (insurance-adjuster approved; GHL opportunity `value_cents` recorded as $0)
**Links:** —

## Context
<!-- human-owned -->

## Log
- 2026-08-12 — created from GHL daily ingest `needs_attention` (priority: high; rank 1 in `stragglers_ranked`): appointment was 118.9 days ago in *Meeting (Scheduled)* CCAM|GHL (30-day stale threshold, 396% of threshold) with zero follow-up since; auto-abandoned today. Contact tagged lead: hot throughout and emailed same-day saying no estimate was ever received — the adjuster-approved claim is at risk of being lost. Needs immediate manual reopen + estimate sent.
- 2026-08-13 — GHL daily ingest `stragglers_ranked` (rank 1): opportunity still shows abandoned even though the Aviva claim is live; adjuster Naushaba Haque is blocked waiting on Titan's line-item repair estimate with photos before approving payment.
- 2026-08-13 — Outlook cross-reference: Pourya resent the estimate to the adjuster Aug 12 and she confirmed she'd review it with Mr. Rajan — the email thread is answered, but the GHL opportunity stage/status hasn't been corrected to match. #admin
- 2026-09-04 — GHL daily ingest, top-level `needs_attention` (high; conversation `kTYnwzFHsJUKSz0ILvOb`): still open, contractor intro + voicemail unanswered 20h. Opportunity status still wrongly marked abandoned in Meeting-Scheduled — not yet corrected. See [[Firoz Rajan]] Log for the Aviva/Outlook cross-reference.
