---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-08-16
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: a6wxJpGrYGT24MCUl53L
ghl_conversation_ids: [scEEaIhErEDwVAmBszW6]
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to: Pourya Lalee
ghl_assigned_to_id: rAMFCiXbAjJOEjtyyvmn
---

# Sabrina Agard

**Contact:** (not provided in today's ingest)
**Address:** (not provided in today's ingest)
**Source:** GHL lead — upstairs carpet replacement (all bedrooms + closets)

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Sabrina Agard - Brampton]]

## Log
- 2026-08-09 — created from GHL daily ingest `needs_attention`: hot-tagged lead, in-home visit booked for Aug 12 (upstairs carpet replacement, all bedrooms + closets); sent project photos today, needs review ahead of the visit. Separately, her GHL opportunity status shows `abandoned` despite this active engagement and booking — a likely data-integrity issue, not real disengagement; needs a manual reopen/status check in GHL. Today's ingest flagged this via a stragglers-list reference (`0h3ZeOEKnYyiqde4Fzwu`) that was not confirmed against her `contact_id`, so treat it as a pointer to check in GHL directly rather than a verified opportunity ID.
- 2026-08-16 — GHL daily ingest `won_records`: **WON $7,706.26 CAD** (opportunity `0h3ZeOEKnYyiqde4Fzwu`, confirms and resolves the 2026-08-09 `abandoned`-status flag — it did in fact close), closed 2026-08-15, carpet-to-hardwood upstairs, Brampton — 6-week cycle from first contact (2026-07-04) to won. Final price negotiated up slightly from the $7,343 mobile quote to $7,706. Payment link sent same day; two unread inbound emails followed (likely the e-transfer receipt) — confirm receipt in GHL before scheduling the project. See [[Sabrina Agard - Brampton]].
