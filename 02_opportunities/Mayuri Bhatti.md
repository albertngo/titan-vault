---
type: opportunity
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: complete
last_activity: 2026-09-27
# Source-system IDs — the join keys. Names are display; IDs are identity.
# ghl_pipeline/stage are names, not IDs: stage IDs are opaque and get renamed in
# the GHL UI, so the name is what a human can verify. The opportunity ID is the anchor.
ghl_opportunity_id: GewzcnR0hclCKNtQq4rZ
ghl_contact_id: jTd0myRrQElIFm2bFDo4
ghl_pipeline: (1) PROJECT: Lead Qualification
ghl_stage: 0a. New Lead
# Operational, not identity: who owns this record in GHL right now (name + id).
ghl_assigned_to: Albert
ghl_assigned_to_id: ooPNab06Ka04uZ1yQ4w6
---

# Mayuri Bhatti

**Client:** [[Mayuri Bhatti]]
**Scope:** Flooring + stairs (custom field "Both")
**Value:** $0.00 (not yet quoted, per GHL)

## Context
<!-- human-owned -->

## Log
- 2026-09-17 — created from GHL daily ingest, top-level `needs_attention` (item 3): opportunity created same day as the contact, landed directly in 0a. New Lead ($0, 0.9 days in stage, no stale risk yet). See [[Mayuri Bhatti]] Log.
- 2026-09-27 — GHL daily ingest, top-level `needs_attention` (item 2, priority: high) + `won_records`: this opportunity moved out of *Meeting (Scheduled)* into **2. *Project Won*** on 2026-09-26, value now **$16,498.00** (this note's frontmatter above still reads the 09-17 record — `ghl_pipeline`, `ghl_stage`, and the Value line are outside this agent's whitelist to edit directly on an existing note; flagging for Albert to backfill `ghl_pipeline: (2) PROJECT: Sales Pipeline`, `ghl_stage: 2. *Project Won*`, and Value: $16,498.00). Lead-to-won in 10 days (Sept 16 → Sept 26): 3 calls, 12 SMS, 5 emails. 35% deposit invoice sent same day for the Sept 28 install/measure visit; not yet confirmed paid. Frontmatter `status` updated active → complete; `last_activity` updated. See [[Mayuri Bhatti]] (client) Log.
