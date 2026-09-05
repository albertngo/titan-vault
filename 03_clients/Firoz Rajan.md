---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: prospect
last_activity: 2026-09-05
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: BpGy2k0bSOHbtzzpsupu
ghl_conversation_ids: [kTYnwzFHsJUKSz0ILvOb]
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to: Pourya Lalee
ghl_assigned_to_id: rAMFCiXbAjJOEjtyyvmn
---

# Firoz Rajan

**Contact:** (not provided in today's ingest)
**Address:** (not provided in today's ingest)
**Source:** GHL lead — insurance-adjuster-approved flooring claim (~$9,000)

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Firoz Rajan - Insurance Claim]]

## Log
- 2026-08-12 — created from GHL daily ingest `needs_attention` / `stragglers_ranked` (rank 1, priority: high): insurance-adjuster-approved claim (~$9,000), tagged lead: hot. Sat in *Meeting (Scheduled)* CCAM|GHL 118.9 days with zero follow-up since the appointment (back in May), then auto-abandoned today (opportunity `ZJvmCRP4R6zbNV2jMqpX`) — while still tagged lead: hot, a direct contradiction. Also carries the undocumented `abandoned-stale` tag alongside `lead: hot`. He emailed the same day saying he never received an estimate. Needs an immediate manual save: reopen, send the estimate, reassure the customer.
- 2026-08-13 — GHL daily ingest `stragglers_ranked` (rank 1) / conversation `kTYnwzFHsJUKSz0ILvOb`: still marked "abandoned" while the Aviva claim is live; adjuster Naushaba Haque is blocked waiting on Titan's line-item repair estimate with photos before she'll approve payment. Needs the estimate sent and the opportunity status corrected.
- 2026-08-13 — Outlook cross-reference (same-day thread, albert@/pourya@): Pourya resent the estimate to the adjuster Aug 12 and she confirmed she'd review it with Mr. Rajan — thread now shows answered on Titan's side, though the opportunity's "abandoned" status (above) hasn't been fixed to match. #admin
- 2026-08-30 — Notion daily ingest (`needs_attention`, Tactical Tasks List rollup): the automated GHL-message follow-up task created for this contact 2026-08-13/14 (insurance adjuster needs the estimate) is still "Needs Verification" and is now 16-17 days stale, buried in today's 114-item stale-task rollup rather than surfaced directly. Not confirmed here whether the 2026-08-13 estimate/status issue above has since been resolved — worth a direct check rather than relying on the tactical-task queue.
- 2026-09-04 — GHL daily ingest, top-level `needs_attention` (high; conversation `kTYnwzFHsJUKSz0ILvOb`): insurance claim thread still stalled — the contractor introduction (forwarded by his insurer) and a voicemail have sat unanswered 20h. Opportunity `ZJvmCRP4R6zbNV2jMqpX` is still wrongly marked abandoned in Meeting-Scheduled despite this live activity; status still not corrected as of this run.
- 2026-09-04 — Outlook daily ingest (48h/72h catch-up window, `sensitivity: private`): his Aviva adjuster (via rajanfiroz73@gmail.com, landed only in pourya@'s inbox) says the claim for 36 Lee Centre Dr unit 601 can be resolved once Titan provides additional floor-area repair details — no reply found in window. Same underlying insurance claim as the GHL thread above, blocking claim payment. #admin
- 2026-09-05 — Outlook daily ingest (`sensitivity: private`): still stuck — his Aviva adjuster (36 Lee Centre Dr unit 601) remains blocked on the same missing floor-area repair details, unanswered since 2026-09-03 (over 24h), continuing to block the claim payout. No new activity found on the GHL side today. #admin
