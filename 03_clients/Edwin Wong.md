---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-09-01
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: none — no GHL contact/opportunity match surfaced in today's ingest; Notion-only payment record
ghl_conversation_ids: []
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to:
ghl_assigned_to_id:
---

# Edwin Wong

**Contact:** (not provided in today's ingest)
**Address:** (not provided in today's ingest)
**Source:** Notion Master Payments Log — no linked Titan Projects row

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
<!-- [[Opportunity Name]] links -->

## Log
- 2026-08-12 — created from Notion daily ingest `payment`: $5,648.00 CAD e-Transfer received 2026-08-11 (auto-deposited, ref C1AXQpNMpybX), clearing the $5,000 flag threshold — https://app.notion.com/3ba596a4505f81d28529d279858d4f5c. No project is linked on the payment row and no matching GHL contact/opportunity surfaced today; needs manual reconciliation to confirm which job this payment applies to.
- 2026-09-01 — Notion daily ingest `new_won_project`: a new Titan Projects row, "Edwin Wong — Mississauga" (full reno/management, 4600 Kimbermount Drive), was created 2026-08-31 — https://app.notion.com/3cd596a4505f800f856ad53188661220. No Opportunity ID, Value Approx, Sales Person, or PM Name captured, so it doesn't cross-reference against GHL or against the 2026-08-12 payment row above. Matched to this note by name only — no source ID ties the two records together, and a full reno in Mississauga vs. an unlinked $5,648 payment aren't confirmed to be the same job. Flagged in today's daily note under Possible duplicates for Albert to confirm whether this is the same Edwin Wong; not merged/assumed here.
