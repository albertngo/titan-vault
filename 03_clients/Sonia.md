---
type: client
visibility: staff
status: active
last_activity: 2026-08-19
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: kEtzpS0JA4eX2VaWLqfy
ghl_conversation_ids: [GqX1jNiTlmO5ROOYNzSk]
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to:
ghl_assigned_to_id:
---

# Sonia

**Contact:** (not provided in today's ingest)
**Address:** Brampton, ON
**Source:** Returning customer — prior project already won/complete

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
None noted yet — returning customer on a follow-on material purchase, not a new pipeline opportunity.

## Log
- 2026-08-05 — created from GHL daily ingest `needs_attention`: booked a new in-home visit for Aug 6, 4:30-5:29pm to look at a follow-on material purchase (prior project already won/complete, so the Meeting-Scheduled 30-day stale window doesn't apply). She asked Albert to confirm the flooring she wants is in stock before the visit — needs a reply before Thursday.
- 2026-08-06 — Still needs an answer: her chosen product (style 6210) is discontinued; asked whether ~600sf can be sourced from another supplier before today's 4:30-5:29pm in-home visit. Flagged again in today's `needs_attention` — answer owed before the visit.
- 2026-08-17 — In-store visit booked yesterday evening (2026-08-16, via the mobile app) for today at 5:00pm at the Brampton store, for the follow-on material purchase; automated SMS confirmation sent (appointment `t3mP0ZHU1Sxi9P1y0jXz`, conversation `GqX1jNiTlmO5ROOYNzSk`).
- 2026-08-19 — Notion daily ingest `new_won_project`: a Titan Projects row for "Sonia Rocha, Brampton" (22 Erindlae cres) shows **WON ~$2,938.90 CAD**, type Flooring — the row has no Opportunity ID, Contact, or Sales Person populated, so it doesn't cross-reference cleanly against GHL. Given this note's Brampton address and her active follow-on-purchase engagement (2026-08-05 through 08-17), this is plausibly the same client under her full name — flagged as a possible match in today's daily note for Albert to confirm (and rename this note to "Sonia Rocha" if so). No opportunity note created pending ID confirmation.
- 2026-08-19 — Outlook customer email (`pourya@`, cc `albert@`): "Sonia Rocha" replied about a quote for 22 Erindale Brampton, asking to remove baseboards throughout after discussing with Corey — received minutes before this pull, too recent to assess as unanswered. Confirms the full name "Sonia Rocha" and the 22 Erindale Brampton address, consistent with the win logged above. #admin
