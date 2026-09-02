---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-09-02
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: kmp6wg2AxP8ENIAxFamH
ghl_conversation_ids: [O6m1zjM9x4o1enBjipoj]
# Operational, not identity: who owns this record in GHL right now (name + id).
# Used to decide whom the next task gets assigned to. Absent = unassigned in GHL.
ghl_assigned_to:
ghl_assigned_to_id:
---

# Clerance Pitters

**Contact:** (not provided in today's ingest)
**Address:** Mississauga, ON
**Source:** Direct — called in, not a form/ad lead

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Clerance Pitters - Mississauga]]

## Log
- 2026-08-09 — created from GHL daily ingest `won_records`: **WON $11,790.00** (closed 2026-08-08, opportunity `xsDmyZ8DmPx57JZcxxWu`). Called in directly on a Saturday (Aug 5) and was quoted with a same-afternoon in-home visit booked within minutes; over the next three days compared the rough quote against another contractor while Titan coordinated a supplier price freeze on his chosen material, Balaton Charm (see [[Greentouch]]), then confirmed with a deposit the day the adjusted quote went out — 3.05 days from visit to win. Contact history: 6 calls, 14 SMS, 2 emails.
- 2026-08-12 — Notion daily ingest `new_won_project` surfaced a likely duplicate data-entry: a second, unmatched Titan Projects row ("Clarance Pittson", $11,719.00, no Opportunity ID/Contact/Sales Person) at the same address, 4798 Huron Heights Dr, Mississauga — https://app.notion.com/3b9596a4505f80c4928ed37f79f3748f. Likely the same $11,790.00 win recorded above entered twice; flagged for Albert to resolve in Notion, not merged here.
- 2026-08-27 — GHL daily ingest `needs_attention` / `stragglers_ranked` (rank 3, category `payment`, conversation `O6m1zjM9x4o1enBjipoj`, contact `kmp6wg2AxP8ENIAxFamH`, priority high): says he sent the e-transfer for the 35% deposit needed before material pickup; GHL has him tagged `lead: warm` but the conversation content reads hot (tag mismatch noted by ingest) — needs confirmation the funds landed today so pickup can proceed.
- 2026-08-30 — GHL daily ingest (`stragglers_ranked` rank 2, conversation `O6m1zjM9x4o1enBjipoj`, contact `kmp6wg2AxP8ENIAxFamH`, priority high, tag_mismatch again flagged warm-vs-hot): e-transferred the **final payment in full on Aug 27** and asked for a receipt reflecting the updated statement — staff acknowledged, but two follow-up emails since (Aug 28, Aug 29) are unanswered. Reply owed today.
- 2026-09-01 — GHL daily ingest (same conversation `O6m1zjM9x4o1enBjipoj`): a written deposit/payment receipt was emailed today, resolving the Aug 28/29 unanswered follow-ups logged above — no outstanding ask per this run.
- 2026-09-01 — Outlook daily ingest (`cpitter01@yahoo.ca`, "4798 Huron Heights Dr" project — same address as the likely-duplicate Notion row logged 2026-08-12, so almost certainly this same client under a third name spelling, "Clarence Pitter"): as of yesterday's scan (2026-08-31 15:06) he was still asking for a paper payment receipt, first raised 2026-08-29 — no reply found in that scan. The GHL receipt logged above today (same-day) plausibly resolves this; worth confirming directly rather than assuming, since the two channels haven't been explicitly tied together. #admin
- 2026-09-02 — Outlook daily ingest, top-level `needs_attention` (49h catch-up window; same message dated 2026-08-31 15:06 already logged above): re-surfaced by the widened window, no reply found yet — the 09-01 assumption that the GHL receipt closed this out has not been confirmed; he is still shown waiting on a paper receipt. Same underlying message, not a new ask — no new fact beyond the 09-01 entry, but the unresolved status persists into today's top-level needs_attention. #admin
