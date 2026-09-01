---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: complete
last_activity: 2026-09-01
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: 3ObSzLss7CNfD5RgHCBB
ghl_conversation_ids: [z4BugAX3Sca4w3lVTuue]
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task goes to. Absent = unassigned in GHL.
ghl_assigned_to: Albert
ghl_assigned_to_id: ooPNab06Ka04uZ1yQ4w6
---

# Allen Giacomelli

**Contact:** allan.g@rogers.com (per Outlook; not yet reconciled into GHL contact fields)
**Address:** (not provided in today's ingest)
**Source:** GHL — completed project (Aug 16), name spelled "Allen Giacomelli" in GHL vs. "Allan Giacomelli" in Outlook — same `allan.g@rogers.com` thread, not yet reconciled to one canonical spelling.

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
None on file yet — no GHL opportunity ID surfaced in today's ingest for the completed project this balance relates to.

## Log
- 2026-09-01 — created from GHL daily ingest, top-level `needs_attention` (conversation `z4BugAX3Sca4w3lVTuue`, `act_immediately`): completed project (closed Aug 16, total $17,967) still has $5,390.10 owing. Albert sent a balance reminder today and the customer enabled Do-Not-Disturb minutes later, blocking further SMS/email — a phone call is now the only channel left. Checked the vault by ID and name before creating — no existing client or opportunity note matched.
- 2026-09-01 — Outlook daily ingest (`allan.g@rogers.com`, matched by content, not the sender-domain admin override — see Outlook `needs_attention` classification note): replying to the GHL balance chase above, he says he'll drop by the store tomorrow after 11am and separately asked for e-transfer details to settle the account. Needs a prompt reply with payment info before that visit — the DND flag above means this Outlook thread (not GHL SMS/email) is now the reliable channel. #admin
