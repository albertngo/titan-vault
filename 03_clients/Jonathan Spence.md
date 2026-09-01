---
type: client
visibility: staff
status: active
last_activity: 2026-09-01
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: 4ZNPHGPIJDd740pSfPzX
ghl_conversation_ids: [xPXoPhdwApx6Bi4igt47]
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to:
ghl_assigned_to_id:
---

# Jonathan Spence

**Contact:** (not provided in today's ingest)
**Address:** (not provided in today's ingest)
**Source:** Existing hot-tagged, completed-project contact (per today's GHL ingest)

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Jonathan Spence]] (opportunity note)

## Log
- 2026-08-06 — created from GHL daily ingest `needs_attention` (anomaly): his in-home visit was rescheduled today to 2026-08-07 10:00am at his request. The reschedule moved his opportunity's stage to *Meeting (Scheduled)*, but the opportunity's `status` has read `abandoned` since 2026-06-15 and was never reopened — a live confirmed appointment is now sitting on a formally closed-out record. See [[Jonathan Spence]] (opportunity) for detail.
- 2026-08-08 — Outlook catch-up run: an Aug 5 email to pourya@ (unreadable via the GHL export, only visible via this Outlook recovery) asked for a quote to retread a section of stairs and tile another area, with a callback request (416-528-8360) — this is the substance behind the Aug 7 rescheduled visit + call already logged above. No separate email reply found, but the GHL follow-up appears to have already resolved this by phone. #admin
- 2026-08-14 — GHL daily ingest `stragglers_ranked` (rank 2, priority: high): repeat hot customer running two active restaurant projects; asked Aug 13 for stairs/vinyl-floor/tile quotes on a 2nd restaurant location, then called again today (Aug 14, sitting 21.6h) which went unanswered with no voicemail — quote request still unaddressed. No GHL opportunity exists yet for the 2nd restaurant, so there's no opportunity ID to attach this to.
- 2026-08-26 — GHL catch-up ingest (same conversation `xPXoPhdwApx6Bi4igt47`, contact `4ZNPHGPIJDd740pSfPzX`, priority high, `stragglers_ranked` rank 4): still no reply to the Aug 14 2nd-restaurant stairs/vinyl/tile quote request — now ~12 days silent from this repeat, high-value commercial customer (2 prior wins, ~$44K+ lifetime).
- 2026-08-30 — Notion daily ingest (`needs_attention`, Tactical Tasks List rollup): the automated GHL-message follow-up task created for this contact 2026-08-13/14 (2nd restaurant quote unanswered) is still "Needs Verification" and is now 16-17 days stale, buried in today's 114-item stale-task rollup rather than surfaced directly — same open 2nd-restaurant quote request logged 08-14/08-26 above, apparently still unaddressed. Worth a direct check rather than relying on the tactical-task queue.
- 2026-09-01 — GHL daily ingest (same conversation `xPXoPhdwApx6Bi4igt47`): today's automated follow-up email finally went out, 17 days after the Aug 14 2nd-restaurant quote request went silent. Not yet confirmed whether this actually contains the stairs/vinyl/tile quote itself or is a generic nurture touch — worth a direct check.
