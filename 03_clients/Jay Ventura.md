---
type: client
visibility: staff
status: active
last_activity: 2026-08-28
# Source-system IDs — the join keys. Names are display; IDs are identity.
ghl_contact_id: Gqgcfut7UGtJTBYgrcud  # was blank/"none" (Notion win row carried no GHL link, and GHL was unreachable/unmatched on 2026-08-07/08) — filled in from today's GHL catch-up ingest, matched by exact name "JAY (VENTURA)" + repeat-customer profile (multiple prior won deals, consistent with this note's history). Not confirmed via a directly-linked opportunity ID; per Identity rule this fills a genuinely blank field rather than overwriting a conflicting one — still worth a direct GHL check to fully confirm.
ghl_conversation_ids: []
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to:
ghl_assigned_to_id:
---

# Jay Ventura

**Contact:** —
**Address:** Oakville, ON (first win) + Beeton, ON (second win, see Opportunities)
**Source:** Notion won-project rows; repeat customer per today's GHL catch-up (multiple prior won deals)

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Jay Ventura - Oakville]]
- [[Jay Ventura - Beeton]]

## Log
- 2026-08-07 — created from Notion daily ingest: new won project, flooring + stairs, Oakville, approx $6,926.00 CAD. No Opportunity ID captured on the Notion row and no Sales Person or PM assigned yet. Checked the vault by name before creating this note — no existing client or opportunity note matched "Jay Ventura" or "Ventura." GHL ingest errored today (MCP tools unreachable), so a live ID cross-check against GHL wasn't possible — flagged in today's daily note as a possible-duplicate follow-up once GHL access is restored.
- 2026-08-08 — Notion daily ingest re-surfaced the same Aug 6 win again (approx $6,926.00 CAD, still no Opportunity ID/Sales Person/PM on the Notion row) — no new information beyond 2026-08-07. GHL ran clean today (234 leads, no errors), but a name search of today's ghl.json still turns up no "Jay Ventura"/"Ventura" contact or opportunity — the data-entry gap flagged 2026-08-07 remains unconfirmed against GHL. Flagged again as a possible duplicate in today's daily note.
- 2026-08-21 — Notion daily ingest `new_won_project`: **WON approx $1,600.00 CAD**, stairs, 47 Carlton Trail, Beeton — a second, separate project from the Oakville win above (distinct Notion page ID, distinct address/amount, not a duplicate). No Opportunity ID/Contact/Sales Person/PM populated on this Notion row either. See new opportunity note [[Jay Ventura - Beeton]].
- 2026-08-21 — GHL catch-up ingest (conversation `swz5n98l8dgNQ0wATsrt`, contact `Gqgcfut7UGtJTBYgrcud`): called Titan 3 times since Aug 14 with no callback logged; an older Meeting-Scheduled opportunity of his also carries an undocumented `abandoned-stale` tag. This is the first GHL contact ID surfaced for this client since the note was created 2026-08-07 without one — matched by exact name + repeat-customer profile; filled into frontmatter above per the Identity rule.
- 2026-08-23 — Notion Master Payments Log: $3,000.00 cash payment received 2026-08-21 against the [[Jay Ventura - Oakville]] win ($6,926.00 CAD) — no sender name recorded on the payment row. See opportunity note for detail.
- 2026-08-28 — Notion daily ingest `work_order_deficiency`: a new QA deficiency Work Order (`WO-Jay Ventura-082826`, Minor, contractor notified same day, $100 CAD budget payout) was created today — client reports the "One Step" product looks too blue. The ingest notes this project matches today's seeded Jay Ventura won-project row but doesn't specify Oakville vs. Beeton; not attributed to a specific opportunity note pending confirmation.
