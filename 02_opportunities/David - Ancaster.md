---
type: opportunity
visibility: staff
status: complete
last_activity: 2026-08-11
# Source-system IDs — the join keys. Names are display; IDs are identity.
ghl_opportunity_id: OE9SsXyefCjOgokqMZMo
ghl_assigned_to: Pourya Lalee
ghl_assigned_to_id: rAMFCiXbAjJOEjtyyvmn
ghl_contact_id: ND7uakleX1tTqBSbXyr2
ghl_pipeline: (2) PROJECT: Sales Pipeline
ghl_stage: *Meeting (Scheduled)* CCAM|GHL
---

# David - Ancaster

**Client:** [[David Rooney]]
**Scope:**
**Value:** $3,565 CAD
**Links:**

## Context
<!-- human-owned -->

## Log
- 2026-07-26 — created from GHL 2-month pull (opportunities created 2026-05-26 → 2026-07-26). Created in GHL 2026-06-29; stage "*Meeting (Scheduled)* CCAM|GHL"; status won; value $3,565 CAD; source store; contact tags: ccam.
- 2026-08-11 — GHL daily ingest: confirmed the opportunity status actually flipped to won on 2026-07-07 (thin contact history — 0 calls, 0 SMS, 2 emails); the pipeline STAGE was only corrected to *Project Won* today, 34 days later — a data-hygiene fix, not a new sale. Excluded from today's `won_today` total. Note: this note's `ghl_stage` frontmatter above still reads the pre-correction stage name (Meeting-Scheduled) — flagging as stale rather than overwriting it, since stage/pipeline frontmatter fields are outside today's write scope.
