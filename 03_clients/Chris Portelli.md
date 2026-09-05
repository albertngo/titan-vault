---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-09-05
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
