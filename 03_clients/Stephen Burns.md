---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-08-27
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: T3m1pm1kSqRmFQJuvAKU
ghl_conversation_ids: []
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to:
ghl_assigned_to_id:
---

# Stephen Burns

**Contact:** (not provided in today's ingest)
**Address:** 200 Kenneth Hobbs Ave, Whitby (per today's Notion win) — see Log for a possible second, Amica Whitby connection
**Source:** Store; repeat account with 2 known won opportunities

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Stephen - Whitby]] (won $21,930, from the 2026-07-26 GHL 2-month pull)
- [[Stephen Burns - Whitby (Amica)]] (won $6,011.04, 2026-08-25)

## Log
- 2026-08-26 — created from GHL daily ingest `won_records`: **WON $6,011.04 CAD** (opportunity `YSL8vqhx64fFyaXI5NSZ`, closed 2026-08-25) — a quote first went out in late January, went quiet for months (mostly automated store nurture), resurfaced in August; a fresh opportunity was created Aug 24 and closed the next day, the fastest close of this window. Matched by contact ID to the existing (previously dangling) `[[Stephen Burns]]` link on the [[Stephen - Whitby]] opportunity note — that note already used this client's full name, but no client note existed until now. See new opportunity note [[Stephen Burns - Whitby (Amica)]].
- 2026-08-26 — Outlook catch-up run (`pourya@`, thread dated 2026-08-21): "Stephen Burns at Amica Whitby" (a retirement residence) asked Pourya to split a back-hall/serveries quote into 3 separate quotes; Pourya has since sent two more (unit 607, Serveries) directly to Amica. Same first+last name and same city (Whitby) as today's win — the win's address (200 Kenneth Hobbs Ave) is plausibly the Amica Whitby community itself, which would make this a commercial repeat account rather than two unrelated residential jobs, but that connection is not source-confirmed. Flagged as a likely link, not asserted. #admin
- 2026-08-27 — Notion daily ingest `new_won_project`: a third Titan Projects row for this client surfaced today — "Stephen Burns, Whitby", 200 kenneth Hobbs Drive, Whitby, **~$30,947.81 CAD**, type Flooring, created 2026-08-26T18:40:43Z — https://app.notion.com/3c8596a4505f803e9d60f8ccd5245268. The row carries no Opportunity ID, no Contact, and no Sales Person, so it doesn't cross-reference cleanly against GHL. Notion's own ingest flags this as a likely duplicate/second-phase of the [[Stephen Burns - Whitby (Amica)]] win logged 2026-08-26 ($6,011.04, same street/city, won ~24h earlier, opportunity `YSL8vqhx64fFyaXI5NSZ`) rather than a third distinct project. Per the Identity rule, not merged and not given its own opportunity note pending an ID — flagged in today's daily note under Possible duplicates for Albert to resolve.
