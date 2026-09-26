---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: prospect
last_activity: 2026-09-26
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: Da9KE2l5o3cLNB8XcNd2
ghl_conversation_ids: [jTC4PIVWXXwIxmwTtmZQ]
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to: Pourya Lalee
ghl_assigned_to_id: rAMFCiXbAjJOEjtyyvmn
---

# Ulupi Babu

**Contact:** (not provided in today's ingest)
**Address:** (not provided in today's ingest)
**Source:** GHL — hot lead, tag `lead: hot`

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
Two open opportunities per today's ingest, neither ID surfaced: a Lead Qualification Hot-stage record and a Sales Pipeline Meeting-Scheduled record ($10,382). No opportunity note created pending an ID.

## Log
- 2026-09-22 — created from GHL daily ingest, top-level `needs_attention` (item 2, priority high, named individually in the "4 Hot leads" cluster) + drift `abandonment_next` (conversation `jTC4PIVWXXwIxmwTtmZQ`): the Hot-stage opportunity is 12.8 days in `0c. ASAP (Hot)` (183% of the 7-day threshold) — past the 14-day auto-abandon point but still open, no `stale_lead` tag; the stage automation looks stuck for this record. Separately, actively engaged as recently as Sept 17 on material/spindle choices for the Meeting-Scheduled opportunity ($10,382) — not an abandoned lead in practice, just an automation miss on the Hot-stage duplicate. Checked the vault by contact ID and name first — no existing client or opportunity note matched.
- 2026-09-26 — GHL daily ingest, top-level `needs_attention` (item 6, named individually) + drift `stale_approaching`/`meeting_no_followup` (contact `Da9KE2l5o3cLNB8XcNd2`): the Hot-stage opportunity (`9d3gzIo8MYIopxOaax9m`) is now 16.8 days in `0c. ASAP (Hot)` — 240% of the 7-day threshold, high severity — no `stale_lead` tag, automation still stuck on this record. The separate Meeting-Scheduled opportunity (`drAAlvrQig3GEGmEMcXC`, $10,382) is now 21.9 days in stage (73% of its 30-day threshold, not yet over) with no follow-up logged since the in-home visit 16.8 days ago (effective window 24.9 of 30). Both remain open concurrently for what still reads as one project — see today's daily note, Possible duplicates (carried over from 2026-09-25).
