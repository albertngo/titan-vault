---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-08-14
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: h5qriQcYT3g2UpfqFStf
ghl_conversation_ids: [nCPpUDIeP3sfrDM6wQAJ]
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to:
ghl_assigned_to_id:
---

# Ricardo Mendoza

**Contact:** (not provided in today's ingest)
**Address:** Mississauga
**Source:** Contractor — repeat client, customer since 2023

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Ricardo Mendoza - Mississauga]]

## Log
- 2026-08-11 — created from GHL daily ingest `won_records`: **WON $9,250 CAD**, stairs + basement flooring, Mississauga (opportunity `52we6fC8KrTgEMEYoyLI`, closed 2026-08-10) — see [[Ricardo Mendoza - Mississauga]]. Repeat contractor client, customer since 2023 (first contact 2023-07-24); deal was effectively already agreed back in March with material picked up in June — today's activity cleaned up several old duplicate opportunities and created/closed a fresh one same-day, a data catch-up rather than a new sale cycle. Contact points: 1 call, 76 SMS, 3 emails.
- 2026-08-12 — Notion daily ingest `new_won_project` surfaced a data-quality issue: two Titan Projects rows share this same Opportunity ID (`52we6fC8KrTgEMEYoyLI`) with different values — GHL `won_records` here records $9,250.00, but a second Notion row carries $10,452.50 (https://app.notion.com/3b9596a4505f8163a501cd7e2490d92c). Needs manual reconciliation in Notion; treating GHL's $9,250.00 as authoritative until resolved.
- 2026-08-13 — Notion daily ingest `new_won_project` on the same Notion page/Opportunity ID (`52we6fC8KrTgEMEYoyLI`, https://app.notion.com/3b9596a4505f8163a501cd7e2490d92c) now reads $5,367.50 CAD — a *third* different value for this one win, after GHL's $9,250.00 (`won_records`, treated as authoritative) and the $10,452.50 logged from this same Notion page on 2026-08-12. The Notion row's value appears to be shifting between ingest runs rather than settling — needs Albert/Notion cleanup, not just a one-time reconciliation; GHL's $9,250.00 remains the figure treated as authoritative here.
- 2026-08-14 — GHL daily ingest `stragglers_ranked` (rank 3, priority: high): a fresh automated deposit-schedule text for [[Ricardo Mendoza - Mississauga]] (sitting 23.5h) got a reply that came back as an empty-body SMS — likely a payment screenshot, unreadable via this ingest pull; check GHL directly to confirm the deposit. Separately, Notion's Master Payments Log recorded a $1,878.63 e-transfer received 2026-08-13 (ref `C1ABnrRU7baD`, not linked to a project row on that end) — unclear whether this is the same payment; needs reconciliation.
