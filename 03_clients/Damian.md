---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-09-02
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: 7jZBuyEYnwITemHcBJoT
ghl_conversation_ids: [bVkz1hPWX0fG6v2xABV7]
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to:
ghl_assigned_to_id:
---

# Damian

**Contact:** (not provided in today's ingest — last name not captured either)
**Address:** (not provided in today's ingest)
**Source:** GHL lead — stairs project

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Damian - Innisfil]]

## Log
- 2026-08-09 — created from GHL daily ingest `needs_attention`: hot-tagged lead with an in-home visit today (2:30-3:29pm) for a stairs project; sent stair-area photos and a flooring sample overnight (6 unread as of ingest, conversation sitting 16.6h with us owing the next response). Review photos/sample before the visit.
- 2026-08-10 — Innisfil stairs job, $4,850 total: confirmed a Wed Aug 12 start and sent a $2,000 partial e-Transfer deposit (GHL conversation `bVkz1hPWX0fG6v2xABV7`; also recorded in Notion's Master Payments Log, ref C1AXwK9mS99u), asking what time the crew arrives. Remaining balance ($2,850) and crew arrival time still need confirming before the install date — flagged in today's needs_attention.
- 2026-08-11 — GHL daily ingest `won_records`: **WON $4,850 CAD** (opportunity `uTBGLp6jqBuFkT9pIiCW`, closed 2026-08-10) — see [[Damian - Innisfil]]. $2,000 e-transfer deposit confirmed by phone (also visible in Notion's Master Payments Log and as an Outlook Interac receipt from Damian Martin); remaining balance now stated as $2,430 (differs from the $2,850 estimate in the 2026-08-10 entry — treat $2,430 as current). Install starts Aug 12 — balance still needs collecting/tracking before the crew starts, flagged again in today's needs_attention.
- 2026-08-12 — Install day: crew confirmed 9-10am arrival for the Innisfil stairs job; customer replied "okay" to the arrival window, no reply needed. $2,430 balance is still outstanding — flagged again in today's needs_attention for on-site collection.
- 2026-08-13 — Notion daily ingest `new_won_project` on the same Opportunity ID (`uTBGLp6jqBuFkT9pIiCW`, https://app.notion.com/3b9596a4505f818388ebe4799c95fcc0) records this win at $4,430.00 CAD, vs. GHL `won_records`' $4,850.00 already logged here — a new $420 discrepancy, separate from the earlier $2,850-vs-$2,430 balance question. GHL's $4,850.00 treated as authoritative pending Notion reconciliation.
- 2026-08-20 — GHL daily ingest `message` (conversation `bVkz1hPWX0fG6v2xABV7`, contact `7jZBuyEYnwITemHcBJoT` — same IDs as this note): inbound "please call me" this morning, sitting 0.4h, us owing the reply. Today's item describes him as a hot lead "with an in-home visit already booked via mobile quote" — that doesn't match the completed/won Innisfil stairs job logged above. Same `ghl_contact_id`, so per the Identity rule this is not a name-only duplicate, but the mismatch in description suggests a possible new/second engagement rather than a stray follow-up on the closed job — flag for Albert to confirm directly in GHL. Callback owed today, flagged in today's `needs_attention`.
- 2026-08-26 — GHL catch-up ingest (same conversation `bVkz1hPWX0fG6v2xABV7`, contact `7jZBuyEYnwITemHcBJoT`, priority high, `stragglers_ranked` rank 1): still unresolved — the ~$2,430 final balance remains uncollected; repeated unreturned call-back requests since Aug 18, now silent 5.8 days. Top-ranked item in today's `stragglers_ranked` and in today's daily-note needs_attention.
- 2026-09-01 — GHL daily ingest (conversation `bVkz1hPWX0fG6v2xABV7`, contact `7jZBuyEYnwITemHcBJoT`): after a long call today, Pourya offered a 2-year warranty extension on the staircase plus a reduced balance of $1,900 (down from the ~$2,430 tracked above) to redo a coat of stain/varnish — awaiting his answer. See [[Damian - Innisfil]].
- 2026-09-02 — GHL daily ingest (same conversation `bVkz1hPWX0fG6v2xABV7`): asked for a date/time for the free staircase-brightening warranty touch-up offered yesterday and gave his email — still waiting on us to schedule it.
- 2026-09-02 — Notion daily ingest `work_order_deficiency` (WO-Damian -090126, https://app.notion.com/3ce596a4505f81d2a594c12e1351827f): a deficiency work order for stain/varnish touchups ($200 budget payout) was created and the contractor notified same day (2026-09-01) — matched by name only, no opportunity ID on the row, but the scope lines up with the staircase-brightening warranty work being scheduled above.
