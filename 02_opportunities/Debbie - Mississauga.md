---
type: opportunity
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: complete
last_activity: 2026-09-13
# Source-system IDs — the join keys. Names are display; IDs are identity.
# ghl_pipeline/stage are names, not IDs: stage IDs are opaque and get renamed in
# the GHL UI, so the name is what a human can verify. The opportunity ID is the anchor.
ghl_opportunity_id: Is8QPInWikdUi0gapDzU
ghl_contact_id: xKPI1HJV9JS4zHqKvzn2
ghl_pipeline: (1) PROJECT: Lead Qualification
ghl_stage: 0b. Later Date (Warm)
# Operational, not identity: who owns this record in GHL right now (name + id).
ghl_assigned_to: Albert
ghl_assigned_to_id: ooPNab06Ka04uZ1yQ4w6
---

# Debbie - Mississauga

**Client:** [[Debbie]]
**Scope:** Condo flooring, ~950sf — comparing Purelux Palace vs Palms samples
**Value:** $7,467.50 CAD (per GHL opportunity record)
**Links:** —

## Context
<!-- human-owned -->

## Log
- 2026-09-08 — created from GHL daily ingest, top-level `needs_attention` (priority: high): 2 days into "0b. Later Date (Warm)" (5% of the 40-day stale threshold, no stale risk); she wants to visit the store today 2-3pm to compare samples in person — needs same-day confirmation. See [[Debbie]] Log.
- 2026-09-09 — GHL daily ingest: **WON $7,989.14 CAD**, moved "0b. Later Date (Warm)" → "2. *Project Won*" today (0.72 days in the new stage at ingest); deposit received in-store. Notion `new_won_project` (https://app.notion.com/3d5596a4505f818bad7cecb1a6b0945c) cross-confirms with a matching Opportunity ID, address 1 Hurontario St #1705, Mississauga, sales rep Pourya Lalee. Follow-up in-home visit booked 2026-10-02 (appointment `lBXJjSYtekVaErly9dcm`) — confirm final-measurements/install-prep purpose. Note: today's won value ($7,989.14) differs from the $7,467.50 in this note's Value line above (set at creation 09-08); not corrected here per append-only convention — flag if it's a true discrepancy rather than a between-ingest value refinement.
- 2026-09-13 — Notion daily ingest `payment` (Master Payments Log, https://app.notion.com/3d6596a4505f816e836dc99b2c1671e6): **$2,796.20 CAD received** via Interac e-Transfer, 2026-09-08, from Debbie Fung, auto-deposited — Projects relation on the payment row is set to this win, so it's a confirmed partial/deposit payment against the $7,989.14 won value above, not just the generic "deposit received in-store" noted on 09-09. GHL still down today (MCP pending approval), so no fresh cross-reference was possible beyond the existing opportunity ID match.
