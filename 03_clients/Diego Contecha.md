---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: complete
last_activity: 2026-09-19
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: GfGkILCpi8ficaPeMdWT
ghl_conversation_ids: [A7ZsHelap1LysZRzb3fu]
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to: Front Desk
ghl_assigned_to_id: edv6p75Y79cYsPS0jPv0
---

# Diego Contecha

**Contact:** (not provided in today's ingest)
**Address:** 88 Germorda Dr, Oakville
**Source:** GHL — repeat customer, demo crew already on site for a new job

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Diego Contecha - Oakville]]

## Log
- 2026-09-04 — created from GHL daily ingest, top-level `needs_attention` (high; conversation `A7ZsHelap1LysZRzb3fu`) + `stragglers_ranked` (rank 1): repeat customer, demo crew already on site for a new Oakville job (88 Germorda Dr); sent tile removal quantities last night, unanswered as of this run (15.1h). The GHL opportunity (`4zS89sPgk9rFNbtJmQDi`, per stragglers_ranked) is wrongly marked abandoned in stage "1b. Postponed" despite this being live, active work — status not yet corrected. Checked the vault by ID and name before creating — no existing client or opportunity note matched.
- 2026-09-08 — Notion daily ingest `new_won_project` (Date Won 2026-09-07, https://app.notion.com/3d4596a4505f80f6baaede447d9419c4): a new won-project row for "Diego Contecha — Oakville," 88 Germorda Drive, Project Type "Both" — same name and exact address as this note, but the row's Opportunity ID, Contact, Value Approx, Sales Person, and PM Name are all blank (same data-entry gap previously flagged for Edwin Wong), so it does not cross-reference to GHL opportunity `4zS89sPgk9rFNbtJmQDi` by ID. Matched here by name + exact address only — treat as very likely the same tile-removal/demo job going from "wrongly marked abandoned" (09-04) to won, but not ID-confirmed. Status set to complete on that basis; flag if a mismatch surfaces. See [[Diego Contecha - Oakville]].
- 2026-09-15 — Notion daily ingest `payment` (Master Payments Log, https://app.notion.com/3dc596a4505f8134854bdd2c8472a39b): **$380.00 CAD received** via Interac e-Transfer, 2026-09-14, from Diego Contecha, auto-deposited. No Projects relation visible on the payment row, so not confirmed against [[Diego Contecha - Oakville]] specifically, but matches this client by sender name — plausibly a balance/final payment on the completed tile-removal/demo job. GHL down again today, no cross-reference possible.
- 2026-09-19 — Notion daily ingest `payment` (Master Payments Log, flagged >= $5,000, https://app.notion.com/3df596a4505f8037a66ff122b8c09016): **$27,700.00 CAD cash** received 2026-09-17, labeled "Cash to Helen + Albert," against a linked project — the largest payment in this window. No Opportunity ID/project name surfaced in today's ingest to confirm which project it's against, and no GHL/Notion ID ties it to this note; matched here by sender first-name "Diego" only (this is the only Diego on file) — not ID-confirmed. Flag if a mismatch surfaces.
