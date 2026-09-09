---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-09-09
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: xKPI1HJV9JS4zHqKvzn2
ghl_conversation_ids: [GokpidGo5fFG88r8WVED]
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to: Albert
ghl_assigned_to_id: ooPNab06Ka04uZ1yQ4w6
---

# Debbie

**Contact:** (not provided in today's ingest)
**Address:** Mississauga (per opportunity contact name "Debbie | Mississauga")
**Source:** GHL lead — condo flooring order, ~950sf

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Debbie - Mississauga]]

## Log
- 2026-09-08 — created from GHL daily ingest, top-level `needs_attention` (conversation `GokpidGo5fFG88r8WVED`, priority: high): comparing Purelux Palace vs Palms samples for a ~950sf condo flooring order; asked to visit the store today between 2-3pm and needs a same-day confirmation. Tagged `lead: warm` in GHL but no `lead:*` tag applied yet — tag/activity mismatch. Checked the vault by ID and name before creating — no existing client or opportunity note matched.
- 2026-09-09 — GHL daily ingest, top-level numbers (`won_today`): **WON $7,989.14 CAD** — deposit received in-store, [[Debbie - Mississauga]] moved from "0b. Later Date (Warm)" to "2. *Project Won*" today. Notion `new_won_project` cross-confirms the same amount (Opportunity ID present, sales rep Pourya Lalee, 1 Hurontario St #1705, Mississauga). A follow-up in-home visit is booked 2026-10-02 — confirm it's for final measurements/install prep per today's brief, not a duplicate consult. Today's won value ($7,989.14) differs from the $7,467.50 recorded in the opportunity note's Value line at creation (09-08) — not corrected here per the append-only rule; see [[Debbie - Mississauga]].
