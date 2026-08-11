---
type: opportunity
visibility: staff
status: complete
last_activity: 2026-08-11
# Source-system IDs — the join keys. Names are display; IDs are identity.
ghl_opportunity_id: 6ze2UFOK6MraSLq5K1w6
ghl_assigned_to: Pourya Lalee
ghl_assigned_to_id: rAMFCiXbAjJOEjtyyvmn
ghl_contact_id: 7gz2qwTPjX1nscMqnhub
ghl_pipeline: (2) PROJECT: Sales Pipeline
ghl_stage: *Meeting (Scheduled)* CCAM|GHL
---

# Jason - Oakville

**Client:** [[Jason Law]]
**Scope:**
**Value:** $22,035 CAD
**Links:**

## Context
<!-- human-owned -->

## Log
- 2026-07-26 — created from GHL 2-month pull (opportunities created 2026-05-26 → 2026-07-26). Created in GHL 2026-06-20; stage "*Meeting (Scheduled)* CCAM|GHL"; status won; value $22,035 CAD; source Referral; contact tags: appt-home.
- 2026-08-11 — GHL daily ingest: confirmed the opportunity status actually flipped to won on 2026-07-07; the pipeline STAGE was only corrected to *Project Won* today, 34 days later — same stage/status lag pattern as [[David - Ancaster]], both touched in the same cleanup batch. Excluded from today's `won_today` total. Note: this note's `ghl_stage` frontmatter above still reads the pre-correction stage name (Meeting-Scheduled) — flagging as stale rather than overwriting it, since stage/pipeline frontmatter fields are outside today's write scope.
