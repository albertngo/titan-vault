---
type: opportunity
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: complete
last_activity: 2026-09-24
# Source-system IDs — the join keys. Names are display; IDs are identity.
# ghl_pipeline/stage are names, not IDs: stage IDs are opaque and get renamed in
# the GHL UI, so the name is what a human can verify. The opportunity ID is the anchor.
ghl_opportunity_id: 2lCJGDSG2exdT4HEinyB
ghl_contact_id: 0rb9addiHloGrKgKaWO1
ghl_pipeline: (2) PROJECT: Sales Pipeline
ghl_stage: "*Meeting (Scheduled)* CCAM|GHL"
# Operational, not identity: who owns this record in GHL right now (name + id).
ghl_assigned_to:
ghl_assigned_to_id:
---

# Agabus Paul

**Client:** [[Agabus Paul]]
**Scope:** Staircase + basement sanding, $2,000 material discount negotiated (per client Log)
**Value:** $11,582.50 CAD (won, per Notion 2026-09-09)
**Links:** Notion project — https://app.notion.com/3d6596a4505f80c81cfd444927738d8

## Context
<!-- human-owned -->

## Log
- 2026-09-09 — created from GHL daily ingest, top-level `needs_attention`: opportunity created directly in "*Meeting (Scheduled)* CCAM|GHL" today (0.89 days in stage, 3% of the 30-day threshold, no stale risk) — the GHL opportunity record flagged missing in [[Agabus Paul]]'s client note (09-08) now exists. An in-home visit already took place 2026-09-08 3:00pm (appointment `gth00tlUvIBjwBsxa0uV`), no follow-up activity logged since (17.4h at ingest).
- 2026-09-10 — Notion daily ingest `new_won_project` (row created 2026-09-09T21:14:08Z): **WON $11,582.50 CAD**, Stairs, 4 Armitage Place, Brampton, Sales Person Pourya Lalee. Matches this opportunity by `ghl_opportunity_id` (Notion's `opp=2lCJGDSG2exdT4HEinyB`) — closes the loop on the 09-09 in-home visit with no GHL `won_records` confirmation possible today (GHL ingest errored). `ghl_pipeline`/`ghl_stage` above are left at their last-known GHL values (not re-verified) since no GHL pull ran today.
- 2026-09-24 — GHL daily ingest (conversation `fVsXxd4aS3ic3cP5T2xa`): color complaint resolved — client accepted a lighter-than-expected red oak stain after Pourya explained the shading, and confirmed another $3,000 sent (total paid now $7,000 of $11,582.50 won value). Site visit locked in for tomorrow to check the finished work.
