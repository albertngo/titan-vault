---
type: opportunity
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-09-09
# Source-system IDs — the join keys. Names are display; IDs are identity.
# ghl_pipeline/stage are names, not IDs: stage IDs are opaque and get renamed in
# the GHL UI, so the name is what a human can verify. The opportunity ID is the anchor.
ghl_opportunity_id: 1rEskj1AX6IgiUz7lTgc
ghl_contact_id: s9IH07J452Kzr7asIToB
ghl_pipeline: (1) PROJECT: Lead Qualification
ghl_stage: 0a. New Lead
# Operational, not identity: who owns this record in GHL right now (name + id).
ghl_assigned_to: Front Desk at Titan Flooring Inc.
ghl_assigned_to_id: edv6p75Y79cYsPS0jPv0
---

# Helena - Warranty

**Client:** [[(647) 919-2118|Helena]]
**Scope:** Warranty case — likely the cracked-tile claim tracked since 2026-07-26 (see client Log)
**Value:** $0.00 (not yet quoted, per GHL)
**Links:** Notion QA Work Order — https://app.notion.com/3d5596a4505f8143b2affe085bf495f8

## Context
<!-- human-owned -->

## Log
- 2026-09-09 — created from GHL daily ingest, top-level `needs_attention` (priority: high): opportunity created today on existing contact `s9IH07J452Kzr7asIToB`, landed in "0a. New Lead", untagged, $0 value, source unknown. Same day, Notion logged a Major-severity Warranty QA Work Order (WO-Helena Toolsiedas-090826, Status: Sent to Projects) and a separate new "Won" project row with no Opportunity ID/contact/value — flagged by Notion's own ingest as likely the same event double-logged. See [[(647) 919-2118|Helena]] Log for the full cross-source picture and an unresolved Toronto/Brampton address mismatch.
