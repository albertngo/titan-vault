---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
# Every triggering item for this note is Outlook-sourced (admin-only surface per
# CONVENTIONS Visibility rule 4) — no GHL/staff-visible source exists for it yet,
# so this note is admin per CONVENTIONS Visibility rule 3's agent-set deviation.
visibility: admin
status: prospect
last_activity: 2026-08-16
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: none — no GHL record found (confirmed against a successful 2026-08-16 GHL run); Outlook-only contact
ghl_conversation_ids: []
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to:
ghl_assigned_to_id:
---

# Frontier Group

**Contact:** Eljona Muzha (estimator, outgoing) — quotes now route to Jack Wu, jackw@frontiergrp.com (new estimator as of 2026-08-14)
**Address:** 1190 Dixie Rd, Mississauga (Lakeview Golf Course kitchen-reno project)
**Source:** Outlook — general contractor requesting a kitchen-renovation construction-services quote

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
None on file — no matching GHL opportunity found.

## Log
- 2026-08-16 — created from Outlook daily ingest `needs_attention` (also flagged 2026-08-14, deferred that day per `01_daily/2026-08-15.md` because GHL ingest had failed and an ID check wasn't possible): Frontier Group's estimator Eljona Muzha emailed `info@` twice on 2026-08-14 (near-identical resend 4 minutes apart) asking that quotes for the 1190 Dixie Rd / Lakeview Golf Course kitchen-reno now go to their new contact Jack Wu (jackw@frontiergrp.com). No reply found in either the 2026-08-14 or 2026-08-16 ingest windows — now over 24h old and unresolved across two runs. #admin
