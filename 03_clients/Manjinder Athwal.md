---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: prospect
last_activity: 2026-09-25
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: Zqf3dAjXvxqvNucUVMrw
ghl_conversation_ids: []
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to:
ghl_assigned_to_id:
---

# Manjinder Athwal

**Contact:** (not provided in today's ingest)
**Address:** Caledon
**Source:** GHL — Lead-Qualification opportunity, tag `ai_qualify`

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Manjinder Athwal - Flooring - Caledon]]

## Log
- 2026-09-25 — created from GHL daily ingest, top-level `needs_attention` (item 4, priority high) + `stragglers_ranked` rank 4 (opportunity `NhPcR8AT7Wdda5UC2YNl`): Lead-Qualification opportunity auto-abandoned today after only 7.04 days in `0a. New Lead` — well short of the documented 14/28-day (stale/abandon) thresholds for that stage. Carries the `ai_qualify` tag; an AI voicemail-calling sequence tried him 4x back in Oct-Nov 2025 on an earlier inquiry and never connected. Looks like `ai_qualify` runs its own faster, undocumented cadence rather than the one in `ghl-workflow.json` — worth confirming with Albert. Checked the vault by ID first (no match), then by name — distinct from the existing [[Manjinder Singh]] (different `ghl_contact_id`, different opportunity, Brampton vs Caledon) — flagging the first-name similarity only, not a duplicate; see the daily note's Possible duplicates.
