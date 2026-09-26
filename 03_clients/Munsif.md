---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-09-26
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: none — not provided by Notion (GHL ingest errored today, no cross-reference possible)
ghl_conversation_ids: []
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to: Pourya Lalee
ghl_assigned_to_id:
---

# Munsif

**Contact:** (not provided in today's ingest)
**Address:** 25 Carlton Street #1006, Toronto
**Source:** Notion Titan Projects — won project

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Munsif - Toronto]]

## Log
- 2026-09-16 — created from Notion daily ingest `new_won_project` (row created 2026-09-15T20:26:31-04:00): **WON $4,068.00 CAD**, Flooring, 25 Carlton Street #1006, Toronto, Sales Person Pourya Lalee. Opportunity ID `pJLQblTWX1TkVD1jsetf` present but no GHL contact ID surfaced (GHL ingest errored today). Checked the vault by opportunity ID and by name first — no existing client or opportunity note matched. See [[Munsif - Toronto]].
- 2026-09-21 — Notion daily ingest `payment`: $1,425.00 CAD e-Transfer received 2026-09-20, no Projects relation linked in Notion — https://app.notion.com/3e2596a4505f81e8a63ace473f5ecfa4. Sender name "Munsifali Molu" reads as a plausible full-name match for this note's "Munsif" (short form), but matched by name only — no source ID on either side to confirm. Flagged in today's daily note under Possible duplicates for Albert to confirm; if correct, this is a second payment following the $4,068.00 win logged 2026-09-16 (see [[Munsif - Toronto]]).
- 2026-09-26 — GHL daily ingest, top-level `needs_attention` (item 5, priority high; conversation `6LLAHZW9qR8QZ5oY4gBr`, contact `qwWs2neAyRVACAIbPhL7` per today's pull — the frontmatter's existing `ghl_contact_id: none` placeholder is not backfilled here, outside this agent's whitelist to edit an existing ID field): flagged Sept 22 that shoe moulding had been removed during install on this won ($4,068.00) job; 4 days later only an automated nurture email has gone out, no personal acknowledgement or resolution. First time this complaint is logged to this note (not captured on this branch on 09-23/24/25).
