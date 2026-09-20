---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: prospect
last_activity: 2026-09-20
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
- 2026-09-08 — GHL daily ingest, by-source summary (conversation `kTYnwzFHsJUKSz0ILvOb`, priority: high): Pourya emailed the adjuster contact info today (Sep 7 4:46pm) after the customer's insurance company reached out to Titan directly back in May — first concrete forward movement since the floor-area repair-detail block flagged 09-04/09-05. Worth confirming the adjuster follow-up landed. See [[Firoz Rajan - Insurance Claim]].
- 2026-09-16 — Outlook daily ingest (`sensitivity: private`; rajanfiroz73@gmail.com, landed only in pourya@'s inbox): the insurance company has approved the claim (36 Lee Centre Dr #601) and he's ready to proceed if Titan sends the paperwork so the insurer pays him directly — no reply found as of this run (~24h). First forward movement since the 09-08 adjuster-contact-info send; see [[Firoz Rajan - Insurance Claim]]. #admin
- 2026-09-17 — GHL daily ingest, top-level `needs_attention` (item 1, high; conversation `kTYnwzFHsJUKSz0ILvOb`): opportunity `ZJvmCRP4R6zbNV2jMqpX` has auto-abandoned again via the stale workflow while the claim is still unresolved (approved per the 09-16 entry above, but Titan hasn't yet sent the insurer the paperwork) — a premature abandonment; needs manual reactivation plus a direct adjuster follow-up.
- 2026-09-17 — Outlook daily ingest (`sensitivity: private`; rajanfiroz73@gmail.com, landed only in pourya@'s inbox): replied 2026-09-16 12:51 directing Pourya to coordinate with a contact named Naushaba (the Aviva adjuster tracked throughout this Log) before discussing any price changes on this repair — no reply found yet (~19.4h since received, approaching the 24h threshold). #admin
- 2026-09-18 — Outlook daily ingest (`sensitivity: private`; rajanfiroz73@gmail.com, pourya@'s inbox only): the Sept 16 12:51 message logged 2026-09-17 as unanswered (~19.4h at that pull, directing Pourya to coordinate with adjuster Naushaba before discussing price) was in fact answered by Pourya on Sept 17 — that message is now closed. The insurance claim itself is still unpaid: Titan has not yet sent the insurer paperwork flagged in yesterday's top-level needs_attention. #admin
- 2026-09-20 — Outlook daily ingest, top-level `needs_attention` (item 5, priority high; `rajanfiroz73@gmail.com`, pourya@'s inbox only): today's pull again shows the 2026-09-16 16:51 ET message (insurer ready to proceed, coordinate via adjuster Naushaba, don't discuss price directly) as unanswered (~91h) — but per the 2026-09-18 entry above, Pourya already replied to this same message on 2026-09-17. Likely a stale resurfacing under this run's widened catch-up window (same branch-isolation pattern flagged elsewhere in today's ingest), not a real regression — worth a quick confirm rather than treating as newly unanswered. The underlying insurance claim (adjuster paperwork) remains the real open item per 09-18. #admin
