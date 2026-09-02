---
type: client
visibility: staff
status: active
last_activity: 2026-09-02
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: yMBiPxHFF2Qa3vUvpeur
ghl_conversation_ids: [lQe1GsXiEf438FdBBcrJ]
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task goes to. Absent = unassigned in GHL.
ghl_assigned_to: Albert
ghl_assigned_to_id: ooPNab06Ka04uZ1yQ4w6
---

# Ashrim Narsinh

**Contact:** (not provided in today's ingest)
**Address:** (not provided in today's ingest)
**Source:** GHL — existing customer, project complete (see [[Ashrim - Milton]])

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Ashrim - Milton]]

## Log
- 2026-09-01 — created from GHL daily ingest, top-level `needs_attention` (conversation `lQe1GsXiEf438FdBBcrJ`): existing customer (project complete) reports the floor is making too much noise and is only home September 7-10 to have it looked at — needs a reply soon to lock a repair date inside that narrow window. Checked the vault by ID before creating: the contact ID already matched the existing [[Ashrim - Milton]] opportunity note, whose Client field has linked to a dangling `[[Ashrim Narsinh]]` since it was created — this note fills that gap.
- 2026-09-02 — GHL daily ingest, top-level `needs_attention` (same conversation `lQe1GsXiEf438FdBBcrJ`, contact `yMBiPxHFF2Qa3vUvpeur`): noise complaint still unresolved, still flagged in today's needs_attention — no new detail beyond the 09-01 report, home window (Sept 7-10) getting closer. We owe a scheduled resolution.
