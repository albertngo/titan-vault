---
type: opportunity
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: complete
last_activity: 2026-08-22
# Source-system IDs — the join keys. Names are display; IDs are identity.
# ghl_pipeline/stage are names, not IDs: stage IDs are opaque and get renamed in
# the GHL UI, so the name is what a human can verify. The opportunity ID is the anchor.
ghl_opportunity_id: 0h3ZeOEKnYyiqde4Fzwu
ghl_contact_id: a6wxJpGrYGT24MCUl53L
ghl_pipeline: (2) PROJECT: Sales Pipeline
ghl_stage: "2. *Project Won*"
# Operational, not identity: who owns this record in GHL right now (name + id).
ghl_assigned_to: Pourya Lalee
ghl_assigned_to_id: rAMFCiXbAjJOEjtyyvmn
---

# Sabrina Agard - Brampton

**Client:** [[Sabrina Agard]]
**Scope:** Carpet-to-hardwood, upstairs bedrooms + closets, Brampton (9 Midnight Lane)
**Value:** $7,706.26 CAD (won 2026-08-15)
**Links:** Notion: https://app.notion.com/3c0596a4505f8079b7ebdf1a9d2facbb

## Context
<!-- human-owned -->

## Log
- 2026-08-16 — created from GHL daily ingest `won_records`: **WON $7,706.26 CAD**, closed 2026-08-15 — 6-week cycle from first contact (2026-07-04) to won; in-home visit 2026-08-12, won 3 days later. Final price negotiated up slightly from the $7,343 mobile quote after Albert held firm on the confirmed hardwood spec; she agreed same day. Contact points: 5 calls, 46 SMS, 4 emails. Payment link sent immediately; two unread inbound emails followed (likely the e-transfer receipt) — confirm receipt in GHL before scheduling.
- 2026-08-19 — Notion daily ingest `new_won_project`: Notion's Titan Projects table now also carries this win (address confirmed as 9 Midnight Lane, Brampton; Sales/PM Pourya Lalee), but the row has a GHL Contact Link and no Opportunity ID, so it doesn't cross-reference cleanly by ID — matched by name + exact value ($7,706.26) to the GHL win already logged 2026-08-16.
- 2026-08-19 — Notion Master Payments Log: $2,697.19 e-transfer received 2026-08-18 from Michael A Agard, not linked to a project row in Notion — but exactly matches 35% of this opportunity's $7,706.26 value ($7,706.26 × 0.35 = $2,697.191), strong circumstantial evidence it's the deposit. Confirm in GHL/QBO.
- 2026-08-19 — Outlook: a customer using the name "Sabrina Crvik" (same 9 Midnight Lane address) confirmed the first deposit was sent and asked Titan to confirm a September 10 install date or offer something earlier; unanswered as of this pull (~15h). Needs a reply given money is already down. #admin
- 2026-08-22 — Outlook catch-up run: same unanswered deposit/install-date thread as 08-19 (`scrvik@gmail.com`) — now 4+ days unanswered, Sept 10 install date confirmation still outstanding. #admin
