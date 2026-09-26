---
type: opportunity
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: complete
last_activity: 2026-09-26
# Source-system IDs — the join keys. Names are display; IDs are identity.
# ghl_pipeline/stage are names, not IDs: stage IDs are opaque and get renamed in
# the GHL UI, so the name is what a human can verify. The opportunity ID is the anchor.
ghl_opportunity_id: 4O7yHvC1pbrGwTDjsvUA
ghl_contact_id: none — not available this run (GHL down; today's Notion row doesn't carry a Contact ID either)
ghl_pipeline: (not provided in today's ingest)
ghl_stage: (not provided in today's ingest)
# Operational, not identity: who owns this record in GHL right now (name + id).
ghl_assigned_to:
ghl_assigned_to_id:
---

# Julie Ann Ohlman - Toronto

**Client:** [[Julie Ann Ohlman]]
**Scope:** Flooring (per Notion Titan Projects row); Outlook references 25 Mackay Avenue
**Value:** $9,819.00 CAD
**Links:** —

## Context
<!-- human-owned -->

## Log
- 2026-09-23 — created from Notion daily ingest cold-start snapshot: Titan Projects row, **$9,819.00 CAD**, opportunity ID `4O7yHvC1pbrGwTDjsvUA` — fell in the 7-day window, withheld from `new_won_project` per the cold-start rule, but this opportunity ID has no existing note anywhere in the vault. GHL was down this run (MCP server pending approval), so pipeline, stage, and contact ID couldn't be cross-checked.
- 2026-09-23 — Outlook daily ingest (`sensitivity: private`): client confirmed acceptance of Pourya's quote for 25 Mackay Avenue — likely the same job as this win, address not independently confirmed against Notion's record. #admin
- 2026-09-24 — GHL daily ingest, top-level `needs_attention` (conversation `M0rVYykQIjQbffSf8O9a`, contact `03cFfrcQl5XDPxScOhL4`): install address sent this morning (25 Mackay Ave, Toronto); the automated 35% deposit payment-schedule text went out the day before. GHL's own conversation summary values this won project at $11,964.89 — differs from the $9,819.00 recorded on the 2026-09-23 Notion row for the same opportunity ID (`4O7yHvC1pbrGwTDjsvUA`); unreconciled, flagging both. A stale duplicate opportunity for the same contact (`IrfgYRy2lVkoYAxkgw9E`, $11,967.89, still open in 0c. ASAP (Hot)) should be closed out now — see the daily note's Possible duplicates.
- 2026-09-24 — Notion daily ingest (Master Payments Log, staff-visible per CONVENTIONS Visibility rule 4): a $1,500.00 CAD deposit e-transfer from Julie Ann Matriz Ohlman was received today; not yet linked to a Projects relation on the Notion side.
- 2026-09-26 — GHL daily ingest drift `stale_approaching` (high, 127% of the 7-day threshold): this won opportunity's stale ASAP-Hot duplicate (`IrfgYRy2lVkoYAxkgw9E`) is now 8.9 days in stage — still open, should be closed. See [[Julie Ann Ohlman]] Log and today's daily note, Possible duplicates.
