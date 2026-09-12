---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-09-12
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: none — not provided by Notion (no Contact Link on the Titan Projects row; GHL ingest also errored today, so no cross-reference was possible)
ghl_conversation_ids: []
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to:
ghl_assigned_to_id:
---

# Jeevan Ramkelawan

**Contact:** (not provided in today's ingest)
**Address:** Mississauga — likely Dwiggin Ave (per a cross-reference in today's Brooks Persad/Judy Ramkelawan Notion row, which cites the same street; not independently confirmed on this row itself)
**Source:** Notion Titan Projects — new won-project row

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Jeevan Ramkelawan - Mississauga]]

## Log
- 2026-09-12 — created from Notion daily ingest `new_won_project` (canonical row created 2026-09-11T21:05:46Z, `opp=Yxb43wEmjLr6EECSllPf`): **WON $1,337.57 CAD**, Mississauga (Notion spells it "Missisauga"). 5 separate Titan Projects rows were created for this same Opportunity ID within ~1.5h on 2026-09-11 — likely a repeated webhook firing; Notion's own ingest deduped to this one canonical row by Opportunity ID, but the 4 duplicate Notion pages remain live and need manual cleanup. Checked the vault by opportunity ID and by name before creating — no existing client or opportunity note matched. See also [[Brooks Persad]] — today's Notion catch-up window carries a separate win row nominally for "Brooks Persad" but internally labeled "Judy Ramkelawan," on the same street (Dwiggin Ave) as this client; flagged as a possible duplicate/identity conflict in today's daily note rather than linked here.
