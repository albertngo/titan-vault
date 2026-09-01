---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: dormant
last_activity: 2026-09-01
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: kQxiUK8760N7We26mBS0
ghl_conversation_ids: []
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task goes to. Absent = unassigned in GHL.
ghl_assigned_to: Pourya Lalee
ghl_assigned_to_id: rAMFCiXbAjJOEjtyyvmn
---

# Fareeda Chand

**Contact:** (not provided in today's ingest)
**Address:** (not provided in today's ingest — linked opportunity is "Fareeda - Etobicoke")
**Source:** (not provided in today's ingest)

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Fareeda - Etobicoke]]

## Log
- 2026-08-31 — created from GHL daily ingest, top-level `needs_attention` (~$83K Meeting-scheduled group, $14.7K of it hers) + drift `meeting_no_followup`/`stale_approaching` (high): the linked opportunity [[Fareeda - Etobicoke]] ($14,690, in-home visit Jun 25) has had zero outbound contact in 67 days, tagged `lead: cold`, 71.7 days in Meeting (Scheduled) — 239% of the 30-day threshold. Checked the vault by ID (`kQxiUK8760N7We26mBS0`) and name before creating — no existing client note matched, even though [[Fareeda - Etobicoke]] (created 2026-07-26) already linked to "Fareeda Chand"; that link was dangling until this note.
- 2026-09-01 — GHL daily ingest, top-level `needs_attention` (conversation `mf49MwVOP184GfJeH5UB`): today's follow-up (after 67 days of silence) got a clear answer — she has decided not to proceed. [[Fareeda - Etobicoke]] is still sitting open in Meeting-scheduled in GHL and should be moved/closed as lost rather than left to go stale. `status` set to `dormant` here to reflect the decline; GHL's own stage/status is unchanged pending that close-out action.
