---
type: client
# Admin: every triggering item is Outlook-sourced (admin-only surface) and this
# client has no GHL record staff can see — see CONVENTIONS: Visibility.
visibility: admin
status: prospect
last_activity: 2026-07-27
# Source-system IDs — the join keys. Names are display; IDs are identity.
ghl_contact_id: none — inbound email lead, no matching GHL record in today's ingest
ghl_conversation_ids: []
outlook_message_id: "<CAGSq0U4mE-rRO1c=HF1k3n=uGtduxKrAP1wMnn=tOisYA=-KkA@mail.gmail.com>"
ghl_assigned_to:
ghl_assigned_to_id:
---

# Allan Parsons

**Contact:** email only, via `info@` (address in Outlook)
**Address:** —
**Source:** inbound email to info@, 2026-07-27

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
None yet.

## Log
- 2026-08-02 — Created from [[Outlook]] catch-up ingest. Homeowner emailed
  `info@` on 2026-07-27 asking for a quote to replace first-floor carpet with 7"
  white oak engineered hardwood (5/8", plywood core). **Still unread, and no
  reply found in Sent Items across the 8-day window** — the highest-priority
  customer item in the first Outlook run. No GHL contact was matched, so this
  lead may exist in [[GHL]] under a different spelling or not at all; reconcile
  and backfill `ghl_contact_id` before working the lead.
