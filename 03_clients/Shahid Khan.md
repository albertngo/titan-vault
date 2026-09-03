---
type: client
visibility: staff
status: prospect
last_activity: 2026-09-03
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: TAPx6WmRYKKV9zHk7Q1Y
ghl_conversation_ids: []
# Operational, not identity: who owns this record in GHL right now (name + id).
ghl_assigned_to: Pourya Lalee
ghl_assigned_to_id: rAMFCiXbAjJOEjtyyvmn
---

# Shahid Khan

**Contact:** (not provided in today's ingest)
**Address:** Brampton

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Shahid Khan]] (opportunity note — Sales Pipeline, Meeting-Scheduled, still open)
- A second opportunity, `10zuagZJvDpALlRC8Vqn` (pipeline "(1) PROJECT: Lead Qualification", stage "0b. Later Date (Warm)", $0 value), was marked `abandoned` today by GHL automation — same contact ID, different opportunity ID. Not written as its own note (no value, no other activity); flagged here as a possible duplicate-opportunity split, same pattern already documented on [[Mizanur Bhuiyan]]. Not merged.

## Log
- 2026-09-03 — created from GHL daily ingest, top-level `needs_attention` (part of the "4 Meeting-Scheduled leads stuck past auto-abandon" cluster, high) + drift `meeting_no_followup` (opportunity `8lVbE6kXysWuEj2gEbMY`): confirmed in-home visit happened 56.0 days ago; just past the 60-day auto-abandon point with no `stale_lead` tag, and the stale/abandon automation isn't wired to this pipeline stage. Same-day, a second GHL opportunity for this contact (`10zuagZJvDpALlRC8Vqn`, $0 value, different pipeline) was auto-abandoned — see Opportunities above. Checked the vault by ID and name before creating — no existing client or opportunity note matched.
