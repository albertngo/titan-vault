---
type: client
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: prospect
last_activity: 2026-09-22
# Source-system IDs — the join keys. Names are display; IDs are identity.
# Agents match on these BEFORE name, so a rename in GHL never creates a duplicate note.
ghl_contact_id: kczIwlqukyaTF0HNQi07
ghl_conversation_ids: []
# Operational, not identity: who owns this record in GHL right now (name + id).
ghl_assigned_to:
ghl_assigned_to_id:
---

# Harry - Brampton

**Contact:** (not provided in today's ingest)
**Address:** Brampton
**Source:** GHL — in-home visit cancelled, unrescheduled

## Context
<!-- human-owned: who they are, what they want, quirks -->

## Opportunities
- [[Harry - Brampton]]

## Log
- 2026-09-09 — created from GHL daily ingest `workflow_drift` (type `meeting_no_followup`, severity high, opportunity `6y80ctYbSu9gTgRbkofR`, 18.7 days overdue): in-home visit was cancelled 48.7 days ago (auto-cancellation SMS sent, asked to reschedule) — no reply and no rebooking since; opportunity still sitting in Meeting-scheduled at 54.8 days in stage, well past the 30-day threshold, with no automation sequence catching it (known workflow gap per today's by-source GHL narrative). Sourced from ghl.json's own `needs_attention` array, not DAILY-BRIEF.md's curated top-7 — flagging for Albert's sanity-check per this agent's still-speculative whitelist. Checked the vault by ID and name before creating — no existing client or opportunity note matched.
- 2026-09-22 — GHL daily ingest, by-source narrative ("Harry's cancelled appointment still uncategorized") + drift `categorization_miss` (high): the Meeting-Scheduled opportunity is now 67.8 days in stage (226% of the 30-day threshold, 61.8 days since the cancelled appointment) — never categorized, never closed out. Same unresolved gap first logged 2026-09-09.
