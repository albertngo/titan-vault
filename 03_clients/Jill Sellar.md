---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-09-02
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: YS83AtRwClqWHaVd5SqD
ghl_conversation_ids: [fHyikKe90f8hrSzpiVFU]
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to: Front Desk
ghl_assigned_to_id: edv6p75Y79cYsPS0jPv0
---

# Jill Sellar

**Contact:** (not provided in today's ingest)
**Address:** (not provided in today's ingest — materials on hold at the warehouse)
**Source:** GHL — store/material customer

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
<!-- [[Opportunity Name]] links -->

## Log
- 2026-08-27 — created from GHL daily ingest `needs_attention` / `stragglers_ranked` (rank 2, category `payment`, conversation `fHyikKe90f8hrSzpiVFU`, contact `YS83AtRwClqWHaVd5SqD`, priority high): materials on hold at the warehouse after her contractor delayed the project; she confirmed today she wants to keep the order and pay the **$1,966.27** balance by e-transfer for a Monday contractor pickup — needs same-day confirmation the balance and pickup logistics are set. Checked the vault by ID and name before creating — no existing client or opportunity note matched. Note: GHL's own `STORE: Material Pipeline` opportunity for her (`MHItKmx7AwbIxy1ICBee`, stage "3. + 8d - Final Follow-up (Auto)") carries `value_cents: 876` ($8.76) — that figure does not match the $1,966.27 balance stated in the conversation; not creating an opportunity note today pending reconciliation of which figure is correct.
- 2026-08-30 — Notion daily ingest (`payment`, Master Payments Log, ref `C1AmnGCCYeUw`): the **$1,966.27** e-Transfer she confirmed sending 2026-08-27 (see above) was received 2026-08-28, auto-deposited — no project row linked on the payment record, but the amount matches exactly. Balance appears settled; the contractor pickup logistics from 08-27 aren't separately confirmed here.
- 2026-09-02 — GHL daily ingest (same conversation `fHyikKe90f8hrSzpiVFU`, contact `YS83AtRwClqWHaVd5SqD`): paid her balance and asked for an updated receipt; we replied within 6 minutes, likely with the receipt attached — resolved.
