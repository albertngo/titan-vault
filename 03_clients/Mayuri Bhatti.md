---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-10-02
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: jTd0myRrQElIFm2bFDo4
ghl_conversation_ids: []
# Operational, not identity: who owns this record in GHL right now (name + id).
ghl_assigned_to: Albert
ghl_assigned_to_id: ooPNab06Ka04uZ1yQ4w6
---

# Mayuri Bhatti

**Contact:** +16479814026
**Address:** (not provided in today's ingest)
**Source:** Website — wants both flooring and stairs

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Mayuri Bhatti]]

## Log
- 2026-09-17 — created from GHL daily ingest, top-level `needs_attention` (item 3, priority: high): new website lead (flooring + stairs, custom field "Both"), landed in 0a. New Lead. Asked directly "do you do house calls for an estimate?" 21+ hours ago with no reply yet — a fresh, responsive lead going cold. Checked the vault by contact ID and name first — no existing client or opportunity note matched.
- 2026-09-27 — GHL daily ingest, top-level `needs_attention` (item 2, priority: high) + `won_records`: opportunity moved to **2. *Project Won*** on 2026-09-26, value **$16,498.00** — fast close from lead intake (Sept 16) to won (Sept 26): 3 calls, 12 SMS, 5 emails in between. A 35% deposit invoice went out the same day to lock the Sept 28 install/measure visit, but payment isn't confirmed yet (conversation `DAQEnXPSQRwEP0ZQWpkY`, next-response-owner: them, flagged `payment-pending`) — needs chasing before the visit. Today's win record shows `ghl_assigned_to` as Pourya Lalee, differing from the Albert on this note's 09-17 frontmatter — outside this agent's whitelist to edit that field directly, flagging for Albert to confirm/backfill. Frontmatter `status` updated prospect → active; `last_activity` updated. See [[Mayuri Bhatti]] (opportunity) Log.
- 2026-09-27 — GHL daily ingest, appointment `visit-mayuri-bhatti-0928`: an in-home visit was booked for Sept 28, 4:00-4:30pm, the same day the project was marked won — reads as the install/measure visit rather than a discovery visit.
- 2026-09-29 — Outlook daily ingest, `needs_attention`: [[Vidar]] asked on Sept 26 for the estimated pick-up date on this order (1350 sqf 7-1/2" Sunset Ash ABC); no reply found from info@. Notion Titan Projects also lists the win (~$16,498, opp ID GewzcnR0hclCKNtQq4rZ). #admin
- 2026-09-30 — Outlook daily ingest (pourya@, private, 2026-09-29): she asked whether the spindle price was cut from 42 to 38 pcs on 4485 Full Moon Circle; Pourya replied 09-29, likely handled. #admin
- 2026-10-01 — Notion daily ingest `payment` (Master Payments Log, row 3ec596a4505f81d6bafef41390eab771): $5,000.00 CAD e-Transfer received 2026-09-30 from "Mayuri S Bhatti" — ≥$5k `needs_attention`. Matched by name only (row has no opportunity ID). Relates to [[Mayuri Bhatti]] opportunity.
- 2026-10-02 — Notion daily ingest `payment` (Master Payments Log, row 3ed596a4505f81dea864f7fc9493762c): $652.68 CAD e-Transfer received 2026-10-01 from "Mayuri S Bhatti". Matched by name only (row has no opportunity ID). With the 09-30 $5,000.00, $5,652.68 received to date against the $16,498.00 project. See [[Mayuri Bhatti]] opportunity.
