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

# John Ap Disposal

**Contact:** (not provided in today's ingest)
**Address:** 20 Donald Avenue, Toronto
**Source:** Notion Titan Projects — new won-project row (Sales Person: Pourya Lalee)

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[John Ap Disposal - Toronto]]

## Log
- 2026-09-10 — created from Notion daily ingest `new_won_project` (row created 2026-09-09T21:13:34Z): **WON $5,800.00 CAD**, Stairs, 20 Donald Avenue, Toronto, Sales Person Pourya Lalee. Opportunity ID present (`Q5swi7OeXZsqXIQKrDN6`) but no Contact Link/GHL contact ID surfaced (GHL ingest errored today — session tool-provisioning gap, no cross-reference possible). Company name reads like a waste-disposal vendor; a same-value ($5,800, `*Meeting (Scheduled)*`) GHL opportunity was flagged 2026-09-01 as a categorization-miss for exactly that reason and declined a note at the time. This win row (Stairs scope, real Sales Person, real address) reads as that same lead having genuinely closed as a retail customer, not a vendor call — worth a quick human check that "John Ap Disposal" is the customer's own name/business rather than a mis-tagged vendor record. Checked the vault by ID and name before creating — no existing client or opportunity note matched.
