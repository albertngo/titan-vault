---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-09-18
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
- 2026-09-06 — GHL daily ingest, top-level `needs_attention` (`stragglers_ranked` rank 2, conversation `scEEaIhErEDwVAmBszW6`, priority high): an inbound email from yesterday is sitting unanswered — install date (Sep 10) and first payment already sent are both live here; reply needed.
- 2026-09-06 — Outlook daily ingest (96h/120h catch-up window; same unanswered thread as before, `scrvik@gmail.com`/9 Midnight Lane, "Sabrina Crvik"): asked for the crew's arrival time on the Sept 10 install date, approaching fast — received under 24h ago so not independently flagged unanswered by Outlook, but worth a same-day reply given the date is close. #admin
- 2026-09-07 — Outlook daily ingest (120h/144h catch-up window; same thread, `scrvik@gmail.com`, "9 Midnight Lane, Brampton quote"): still no reply found as of this pull — the unresolved "Sabrina Crvik" name-variant flag from 2026-08-19 remains open (no GHL ID ties the two records together); install date is now imminent (Sep 10). #admin
- 2026-09-08 — Outlook daily ingest (`sensitivity: private`): "Sabrina Crvik" thread now **resolved** — she and Pourya finished confirming Sept 10 move-out prep (pack away small items, clothing, sentimental items) after his arrival-window reply; thread closed with a thank-you from her, no reply needed. Closes out the unanswered stretch logged 08-19 through 09-07. The "Crvik"/Agard name-variant question (no GHL ID ties the two records) remains open but is no longer time-pressured. #admin
- 2026-09-08 — GHL daily ingest (same conversation `scEEaIhErEDwVAmBszW6`, priority: normal): two inbound emails today (Sep 7, empty body) likely carry an attachment/receipt — low urgency, just confirm they came through ahead of the Sep 10 install.
- 2026-09-18 — Notion daily ingest `payment` (Master Payments Log): a further $3,000.00 CAD e-Transfer received 2026-09-17 from Michael A Agard (ref `C1A6KqtNBCXk`), not linked to a project row in Notion — https://app.notion.com/3df596a4505f81aab229e7f7129deae2. Same payer name flagged 2026-08-19 as plausibly (not source-confirmed) tied to this client's 35% deposit ($2,697.19); this is a separate, later payment from the same name — still unconfirmed against [[Sabrina Agard - Brampton]].
