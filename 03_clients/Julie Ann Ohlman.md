---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-09-25
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: none — not available this run (GHL ingest errored; no ID surfaced in the Notion or Outlook items either)
ghl_conversation_ids: []
# Operational, not identity: who owns this record in GHL right now (name + id).
ghl_assigned_to:
ghl_assigned_to_id:
---

# Julie Ann Ohlman

**Contact:** (not provided in today's ingest)
**Address:** Toronto (per Notion Titan Projects row); Outlook references 25 Mackay Avenue for the same name — not independently cross-confirmed against Notion's own address field
**Source:** Notion Titan Projects win, cross-referenced against an Outlook quote-acceptance email

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Julie Ann Ohlman - Toronto]]

## Log
- 2026-09-23 — created from Notion daily ingest cold-start snapshot: a Titan Projects row for **Julie Ann Ohlman, Toronto — $9,819.00 CAD** (opportunity `4O7yHvC1pbrGwTDjsvUA`) fell in the 7-day window; withheld from `new_won_project` by today's cold-start rule, but genuinely new against this vault (no prior note, no matching log entry anywhere). GHL was down this run (MCP server pending approval), so the opportunity's contact ID, pipeline, and stage couldn't be independently verified. No `ghl_contact_id` was available to check first, so matched by name — no existing client or opportunity note matched. See new opportunity note [[Julie Ann Ohlman - Toronto]].
- 2026-09-23 — Outlook daily ingest (`sensitivity: private`, landed in albert@): confirmed she's happy with Pourya's quote for 25 Mackay Avenue ("Sounds good, thank you") — same name as today's Notion win, plausibly the same job closing out; address not independently confirmed against Notion's own city field, so not asserted as certain. #admin
- 2026-09-24 — GHL daily ingest, top-level `needs_attention` (conversation `M0rVYykQIjQbffSf8O9a`, contact `03cFfrcQl5XDPxScOhL4`, priority: high): install address sent this morning (25 Mackay Ave, Toronto), a day after the automated 35% deposit payment-schedule text went out. Confirm the deposit landed and that the address is logged for scheduling. Note a real contact ID surfaced today (`03cFfrcQl5XDPxScOhL4`) and a real won-opportunity ID (`4O7yHvC1pbrGwTDjsvUA`, value $11,964.89 per this conversation vs $9,819.00 per the 2026-09-23 Notion row — unreconciled, flagging both) — the client/opportunity frontmatter still reads "none" from 09-23's GHL outage; outside this agent's whitelist to edit existing ID fields, so flagging for Albert to backfill. Also: a stale duplicate opportunity for the same contact (`IrfgYRy2lVkoYAxkgw9E`, $11,967.89, 0c. ASAP (Hot), 98.6% to its own stale threshold) should be closed out now that the project is won — see Possible duplicates.
- 2026-09-24 — Notion daily ingest (Master Payments Log, staff-visible per CONVENTIONS Visibility rule 4): a $1,500.00 CAD Interac e-transfer from Julie Ann Matriz Ohlman was received and auto-deposited today; no Projects relation linked on the Notion row yet, but the sender name matches this won project.
- 2026-09-24 — Outlook daily ingest (`sensitivity` unset, defaults private per source_defaults → admin): info@ received 10 live-chat notifications plus an appointment-reschedule note from her this week, most still unread (content only visible in the chat platform itself, not email). #admin
- 2026-09-25 — Outlook daily ingest (`sensitivity` unset, defaults private per source_defaults → admin): live-chat/appointment-notice count is now 11 (up from 10 yesterday), including one appointment-reschedule alert routed to pourya@ this time — still no Outlook reply found for any of them (caveat unchanged: GHL live-chat replies go out through GHL, not Outlook, so this isn't confirmed as actually unanswered). Same $1,500 Interac deposit already logged 2026-09-24 (Notion), not re-counted here. The 2026-09-24 deposit-schedule/install-date confirmation ask (see that entry) is still unconfirmed as of this pull. #admin
