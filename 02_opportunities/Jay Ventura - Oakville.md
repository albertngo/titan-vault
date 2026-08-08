---
type: opportunity
visibility: staff
status: complete
last_activity: 2026-08-08
# Source-system IDs — the join keys. Names are display; IDs are identity.
# ghl_pipeline/stage are names, not IDs: stage IDs are opaque and get renamed in
# the GHL UI, so the name is what a human can verify. The opportunity ID is the anchor.
ghl_opportunity_id: none — not captured on the Notion win row (page created without a GHL link)
ghl_contact_id: none — GHL ingest errored 2026-08-07 (MCP unreachable); still no name match found in the 2026-08-08 pull either
ghl_pipeline:
ghl_stage:
# Operational, not identity: who owns this record in GHL right now (name + id).
ghl_assigned_to:
ghl_assigned_to_id:
---

# Jay Ventura - Oakville

**Client:** [[Jay Ventura]]
**Scope:** Flooring + stairs, Oakville ON
**Value:** $6,926.00 CAD (Notion)
**Links:** Notion project — https://app.notion.com/3b4596a4505f80b2b168cfd288eb7a62

## Context
<!-- human-owned -->

## Log
- 2026-08-07 — Won project surfaced via Notion daily ingest, approx $6,926.00 CAD, flooring + stairs, Oakville. No GHL Opportunity ID captured on this Notion row and no Sales Person/PM assigned yet. GHL ingest errored today (MCP tools unreachable) so this couldn't be cross-referenced against GHL opportunities/contacts — flagged for a duplicate check once GHL access is restored.
- 2026-08-08 — Notion daily ingest re-surfaced the same win again, no new detail beyond 2026-08-07. GHL ran without error today but a name search of today's ghl.json still turns up no "Jay Ventura"/"Ventura" record — worth a direct GHL search (not just today's ingest window) to resolve the missing Opportunity ID before this is treated as fully reconciled.
