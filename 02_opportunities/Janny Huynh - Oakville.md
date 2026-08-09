---
type: opportunity
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: complete
last_activity: 2026-08-09
# Source-system IDs — the join keys. Names are display; IDs are identity.
# ghl_pipeline/stage are names, not IDs: stage IDs are opaque and get renamed in
# the GHL UI, so the name is what a human can verify. The opportunity ID is the anchor.
ghl_opportunity_id: lEnguXnw4rw9C1WfsUcL
ghl_contact_id: t7Tpu8ErycS60n8w8xgr
ghl_pipeline: (2) PROJECT: Sales Pipeline
ghl_stage: 2. *Project Won*
# Operational, not identity: who owns this record in GHL right now (name + id).
ghl_assigned_to:
ghl_assigned_to_id:
---

# Janny Huynh - Oakville

**Client:** [[Janny Huynh]]
**Scope:** 3 rooms measured, Oakville (2426 Shadow Crt) — referral/friend deal, quote reportedly already handled informally
**Value:** $4,145.00 CAD (won 2026-08-08)
**Links:** Notion project (canonical row) — https://app.notion.com/3b2596a4505f81f39b96c67234b879b1

## Context
<!-- human-owned -->

## Log
- 2026-08-04 — created from Notion daily ingest `new_won_project`. Created directly in (2) PROJECT: Sales Pipeline, stage *Meeting (Scheduled)*, skipping Lead Qualification entirely — consistent with this being a pre-arranged/referred deal, not a normal inbound lead. In-home visit confirmed today 5:15-5:45pm; she sent photos of the 3 rooms ahead of the visit (Triforest Sable, FAW Montana samples mentioned). Notion's Titan Projects table already logged this as a won project (sales: Pourya Lalee, no PM/value assigned yet) even though the GHL stage hasn't moved to Won — mismatch not yet reconciled. Notion row was duplicated 5x within ~17 minutes on creation (same Opportunity ID, likely an automation retry loop); canonical row is the earliest (02:23:51Z), 4 stray duplicate rows still need manual cleanup.
- 2026-08-09 — GHL daily ingest `won_records`: **WON $4,145.00**, closed 2026-08-08 — GHL stage moved to *Project Won*, resolving the 2026-08-04 stage/system mismatch. Her preferred color was discontinued; Titan sourced a custom-order alternative (Hardwood Giant, 2-3 week lead) and sent the official estimate, which she accepted with an Aug 26-28 install window. Contact points: 0 calls, 4 SMS, 1 email. Still no PM assigned per Notion.
