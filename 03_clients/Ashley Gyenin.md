---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-08-26
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: dpW9q5uEvrGwEbDHmTIA
ghl_conversation_ids: [65u1YnpclpCF4CPFITWD]
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to: Albert Ngo
ghl_assigned_to_id: ooPNab06Ka04uZ1yQ4w6
---

# Ashley Gyenin

**Contact:** email domain `saradal.ca` (from Outlook; full address not captured); no phone on file
**Address:** 16 Yonge St (GHL) / 15 Viking #1903 (Outlook) — unit references differ across sources, not yet reconciled
**Source:** Old commercial flooring invoice contact (GHL); invoice originally sent 2026-07-28

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
None captured in today's ingest — no GHL opportunity ID surfaced.

## Log
- 2026-08-26 — created from GHL daily ingest `stragglers_ranked` (rank 12, category `payment`, conversation `65u1YnpclpCF4CPFITWD`, contact `dpW9q5uEvrGwEbDHmTIA`, priority high): an old commercial flooring invoice contact (16 Yonge St job, invoiced Jul 28) replied by email today asking Titan to confirm whether payment for a unit went through, after a long gap — unclear if this is still an active job. Checked the vault by ID and name before creating — no existing client or opportunity note matched.
- 2026-08-26 — Outlook catch-up run (thread with albert@, domain `saradal.ca`, 2026-08-25 15:22): a same-window message matched by content (payment-confirmation request, same "unit" framing) supplies the full name "Ashley Gyenin" and a second address, 15 Viking #1903 — she asked Albert to confirm the e-transfer payment went through, saying she'll pay the unit owner directly if not. No reply on file yet (under the 24h threshold at scan time). Name and second address are Outlook-only; not yet confirmed against GHL. #admin
