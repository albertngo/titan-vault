---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-09-23
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
