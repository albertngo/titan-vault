---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-10-05
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: ewY17VHX12nHpcxkRsCm
ghl_conversation_ids: [vilWo1LPUurzPr1EFw47]
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to: Pourya Lalee
ghl_assigned_to_id: rAMFCiXbAjJOEjtyyvmn
---

# Chris Portelli

**Contact:** — (not provided in today's ingest)
**Address:** 7114 Fayette Circle, Mississauga, ON (red-roof house — given by the customer 2026-09-05, needs confirming in file)
**Source:** GHL — Meta ad (Before/After), tagged lead: hot

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Chris Portelli - Mississauga]]

## Log
- 2026-09-05 — created from GHL daily ingest, top-level `needs_attention` / `stragglers_ranked` (rank 2): hot lead who booked an in-home visit for Sept 9 (2:30pm); replied today with his address (7114 Fayette Circle, Mississauga — red-roof house) for the appointment, sitting 11.2h unanswered as of ingest — needs confirming in file before the visit. Checked the vault by contact ID (`ewY17VHX12nHpcxkRsCm`) and by name first — no existing match. Also flagged today: GHL auto-created a second, duplicate "0a. New Lead" opportunity (`CL8HcPCIC8r2XkRwn1wY`) for this same contact even though he already has an active Meeting-Scheduled opportunity — a data-hygiene quirk, not a second real deal; not written up as a separate opportunity note.
- 2026-09-19 — GHL daily ingest, top-level `needs_attention` (item 8; `stragglers_ranked` rank 1, opportunity `UJZ8TIWgY9ZCjY5fTsRv`): his Meeting-Scheduled opportunity ($2,441.68, still tagged `lead: hot`) is carrying a `stale_lead` tag at only 14.7 days into the 30-day stage threshold (49%) — looks carried over from a different, older opportunity on the same contact rather than a real staleness read on this active deal, and risks triggering a premature stale/abandon cascade. No new customer contact today; flagging the tag-hygiene risk only. See [[Chris Portelli - Mississauga]].
- 2026-09-27 — GHL daily ingest, top-level `needs_attention` (item 4, named individually) + drift `meeting_no_followup` (high, opportunity `UJZ8TIWgY9ZCjY5fTsRv`): now 22.7 days in Meeting (Scheduled) with zero contact since the Sept 9 in-home visit — last outbound was Sept 6, 3 days BEFORE the visit. Still tagged `stale_lead` even though the stage's 30-day threshold hasn't been reached yet, consistent with the tag-hygiene risk flagged 2026-09-19. One of today's individually-surfaced meeting-scheduled drift findings behind the brief's wider structural finding for this stage. See [[Chris Portelli - Mississauga]].
- 2026-10-05 — GHL daily ingest (re-pull 2026-10-05), drift `meeting_no_followup` (high): visit held 2026-09-09, no text or call in 26 days; stage at 31 of 30 days (stale_lead already applied). See [[Chris Portelli - Mississauga]].
