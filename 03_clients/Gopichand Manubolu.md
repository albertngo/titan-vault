---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: prospect
last_activity: 2026-09-11
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: xlFLLV6VYweQOxRpoVkQ
ghl_conversation_ids: [vgJCujk8x3WJhQsrbRHX]
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task goes to. Absent = unassigned in GHL.
ghl_assigned_to: Front Desk
ghl_assigned_to_id: edv6p75Y79cYsPS0jPv0
---

# Gopichand Manubolu

**Contact:** (not provided in today's ingest)
**Address:** (not provided in today's ingest)
**Source:** GHL lead — hot-tagged, $1,885 quote

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Gopichand Manubolu]] (opportunity note)

## Log
- 2026-09-06 — created from GHL daily ingest, top-level `needs_attention` (rank 1 in today's `stragglers_ranked`; conversation `vgJCujk8x3WJhQsrbRHX`, priority high): hot lead ($1,885) directly asked "do you guys work on Sunday? I am only free on Sunday" ~20h ago with zero reply — his opportunity was already auto-abandoned Sep 4, a day before he wrote back wanting to proceed. Checked the vault by contact ID (`xlFLLV6VYweQOxRpoVkQ`) and name first — no existing match. No opportunity note created; today's ingest carries no opportunity ID for this deal, only the conversation reference.
- 2026-09-11 — GHL daily ingest, top-level `needs_attention` + drift `categorization_miss` (high, opportunity `CRvAePrqvV2jZmtWAvgi` now identified): still shows 'abandoned' since Sept 4, but the conversation shows a live pricing/scheduling exchange as recently as yesterday (he asked about Sunday work; we explained a site visit is needed to confirm sqft) — the auto-abandon fired mid-negotiation, same pattern as the Michael Camara finding on 2026-09-08. Re-open and schedule the visit rather than treat as dead. Opportunity ID now available — created [[Gopichand Manubolu]] (opportunity) note.
