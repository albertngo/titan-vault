---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-08-30
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: TmQX8DQ8tTb2fU2MRIlK
ghl_conversation_ids: [W6B8wfM9s4PnfehckwUI]
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to: Front Desk
ghl_assigned_to_id: edv6p75Y79cYsPS0jPv0
---

# Michael Camara

**Contact:** (not provided in today's GHL ingest)
**Address:** (not provided in today's GHL ingest)
**Source:** GHL — past customer (project won Dec 2025), now referring a friend for a new quote

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
<!-- none yet — the friend's referral quote isn't a formalized GHL opportunity yet -->

## Log
- 2026-08-22 — created from GHL daily ingest `needs_attention` (conversation `W6B8wfM9s4PnfehckwUI`, priority: high): past customer (project won Dec 2025) referring a friend who needs a 525sf vinyl install + carpet/laminate removal quote for a condo. He's asked twice (Aug 19, Aug 21) whether the quote was sent — it still hasn't gone out, 21+ hours since his last message. He's also unsure whether Titan has his friend's email on file. Send the overdue quote.
- 2026-08-30 — GHL daily ingest (`stragglers_ranked` rank 5, workflow_drift `stale_approaching`, priority high): an open opportunity now on file under this name (`DHrlkU4mjciQ1OY2BUv4`, stage "0c. ASAP (Hot)") is ~1 day from the 7-day stale_lead mark (84% of threshold) — contact today before automation tags it stale. Today's ingest doesn't supply a `contact_id` on this opportunity record, so it's matched here by name only (single Michael Camara record in the vault); flag if a mismatch surfaces. No separate opportunity note created this run — not part of today's curated top-level needs_attention (only in the by-source GHL summary); revisit if it recurs or escalates.
