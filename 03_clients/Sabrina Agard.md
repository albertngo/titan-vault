---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-08-25
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: a6wxJpGrYGT24MCUl53L
ghl_conversation_ids: [scEEaIhErEDwVAmBszW6]
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to: Pourya Lalee
ghl_assigned_to_id: rAMFCiXbAjJOEjtyyvmn
---

# Sabrina Agard

**Contact:** (not provided in today's ingest)
**Address:** (not provided in today's ingest)
**Source:** GHL lead — upstairs carpet replacement (all bedrooms + closets)

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Sabrina Agard - Brampton]]

## Log
- 2026-08-09 — created from GHL daily ingest `needs_attention`: hot-tagged lead, in-home visit booked for Aug 12 (upstairs carpet replacement, all bedrooms + closets); sent project photos today, needs review ahead of the visit. Separately, her GHL opportunity status shows `abandoned` despite this active engagement and booking — a likely data-integrity issue, not real disengagement; needs a manual reopen/status check in GHL. Today's ingest flagged this via a stragglers-list reference (`0h3ZeOEKnYyiqde4Fzwu`) that was not confirmed against her `contact_id`, so treat it as a pointer to check in GHL directly rather than a verified opportunity ID.
- 2026-08-16 — GHL daily ingest `won_records`: **WON $7,706.26 CAD** (opportunity `0h3ZeOEKnYyiqde4Fzwu`, confirms and resolves the 2026-08-09 `abandoned`-status flag — it did in fact close), closed 2026-08-15, carpet-to-hardwood upstairs, Brampton — 6-week cycle from first contact (2026-07-04) to won. Final price negotiated up slightly from the $7,343 mobile quote to $7,706. Payment link sent same day; two unread inbound emails followed (likely the e-transfer receipt) — confirm receipt in GHL before scheduling the project. See [[Sabrina Agard - Brampton]].
- 2026-08-19 — Notion daily ingest `new_won_project` re-confirms the win above via the Titan Projects table: address 9 Midnight Lane, Brampton; Sales/PM Pourya Lalee. The row carries a GHL Contact Link but no Opportunity ID, so it doesn't cross-reference cleanly by ID alone — matched here by name and exact value ($7,706.26) against the win already logged 2026-08-16. Separately, Notion's Master Payments Log recorded a $2,697.19 e-transfer from Michael A Agard (2026-08-18, ref `C1ACmDxyAM8k`), not linked to a project row — but $7,706.26 × 35% = $2,697.191, an exact match to the standard 35% deposit on her win, strong (not source-confirmed) evidence this is her deposit. See [[Sabrina Agard - Brampton]].
- 2026-08-19 — Outlook customer email (`pourya@`, cc `albert@`): a "Sabrina Crvik" (scrvik@gmail.com) said she sent the first deposit for 9 Midnight Lane, Brampton — the same address as this client's win — and asked Titan to confirm a September 10 install date or offer something earlier; no reply found in Sent items as of this pull (~15h). "Crvik" is a name variant/different surname for what's very likely the same person (address + project match) — flagged, not merged; confirm the install date given money is already down. #admin
- 2026-08-22 — Outlook catch-up run (same `pourya@`/`albert@` thread as 08-19, from "Sabrina Crvik" scrvik@gmail.com, 9 Midnight Lane): still no reply found — now 4+ days since she confirmed the deposit was sent and asked to confirm the Sept 10 install date or move it earlier. Needs a reply given money is already down. #admin
- 2026-08-23 — Outlook catch-up run (168h/192h widened window; same thread, `scrvik@gmail.com`): still no reply found — now 5+ days since the deposit confirmation and Sept 10 install-date question. Recurring unresolved item, unchanged from 08-22 beyond elapsed time. #admin
- 2026-08-24 — Outlook catch-up run (168h/192h window; same thread, `scrvik@gmail.com`, 9 Midnight Lane): still no reply found — now 6+ days since the deposit confirmation and Sept 10 install-date question. Recurring unresolved item, unchanged beyond elapsed time. #admin
- 2026-08-25 — Outlook catch-up run (168h/192h window; same thread, `scrvik@gmail.com`, 9 Midnight Lane): still no reply found — now 6+ days since the deposit confirmation and Sept 10 install-date question, ranked #2 in today's needs_attention. Recurring unresolved item, unchanged beyond elapsed time. #admin
