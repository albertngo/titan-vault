---
type: client
status: prospect
last_activity: {{date}}
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id:
ghl_conversation_ids: []
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to:
ghl_assigned_to_id:
---

# {{name}}

**Contact:**
**Address:**
**Source:** <!-- GHL lead / referral / walk-in -->

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
<!-- [[Opportunity Name]] links -->

## Log
- {{date}} — created from ingest
