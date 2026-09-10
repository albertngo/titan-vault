---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-09-10
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: none — not provided by Notion (no Contact Link on the Titan Projects row; GHL ingest also errored today, so no cross-reference was possible)
ghl_conversation_ids: []
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to:
ghl_assigned_to_id:
---

# Mien

**Contact:** (not provided in today's ingest)
**Address:** 2096 Westmount Dr, Oakville
**Source:** Notion Titan Projects — new won-project row, no Opportunity ID/Contact Link/Sales Person filled in

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Mien - Oakville]]

## Log
- 2026-09-10 — created from Notion daily ingest `new_won_project` (row created 2026-09-09T13:26:20Z): **WON $1,645.00 CAD**, Flooring, 2096 Westmount Dr, Oakville. Row's own Description reads "Random Project [David]" — unexplained; no Opportunity ID, Contact Link, or Sales Person on the row, so this doesn't cross-reference against GHL. Matched by name + address only (fell back to the Notion page url as the stable key: https://app.notion.com/3d6596a4505f806fb557c62207271936). Checked the vault by ID and name before creating — no existing client or opportunity note matched.
