---
type: opportunity
# Note floor: staff may see this note; admin-grade bullets carry a trailing #admin
# (see CONVENTIONS: Visibility). Set admin only when the whole entity is admin-sourced.
visibility: staff
status: active
last_activity: 2026-09-25
# Source-system IDs — the join keys. Names are display; IDs are identity.
# ghl_pipeline/stage are names, not IDs: stage IDs are opaque and get renamed in
# the GHL UI, so the name is what a human can verify. The opportunity ID is the anchor.
ghl_opportunity_id: s7xopkaqhcvzFuqaqTOt
ghl_contact_id: zmlvYiQyRyUQ3bzLkN3D
ghl_pipeline: (2) PROJECT: Sales Pipeline
ghl_stage: "*Meeting (Scheduled)* CCAM|GHL"
# Operational, not identity: who owns this record in GHL right now (name + id).
ghl_assigned_to:
ghl_assigned_to_id:
---

# Arvind - Mississauga

**Client:** [[Arvind]]
**Scope:** (not specified in today's ingest — landed directly in Meeting Scheduled via Meta Ad)
**Value:** $0.00 (not yet quoted, per GHL)
**Links:** —

## Context
<!-- human-owned -->

## Log
- 2026-09-09 — created from GHL daily ingest, top-level `needs_attention`: opportunity created directly in "*Meeting (Scheduled)* CCAM|GHL" (0.57 days in stage, 2% of the 30-day threshold, no stale risk); in-home visit booked today 4:30pm (appointment `FjWbNMyTiP86sjPhA6pt`), customer asked for a confirmation call an hour ahead. See [[Arvind]] Log.
- 2026-09-17 — GHL daily ingest, by-source finding (high): now valued $14,476.95 (per today's pull), 8.6 days in Meeting-Scheduled, no stale risk — but the client told us Sept 12 he's "decided to go with another company." A duplicate $0 opportunity also remains open on this contact in 0c. ASAP (Hot) (`nPph9lPInN7Dxj4nz8Ps`). Today's brief recommends closing both as lost; GHL still shows both open as of this run. See [[Arvind]] Log.
- 2026-09-25 — GHL daily ingest, top-level `needs_attention` (item 2, priority high) + `stragglers_ranked` rank 1 (opportunity `s7xopkaqhcvzFuqaqTOt`): client explicitly declined this morning ("gone with someone else"), confirming the Sept 12 hearsay logged 2026-09-17. The nurture automation sent an identical templated SMS 3 minutes after the decline (the 4th send of this exact message since Sept 17); same duplicate-send bug hit 5 other lead:hot contacts yesterday. Should be moved to lost and the automation sequence paused/investigated — not yet done as of this pull. See [[Arvind]] Log.
