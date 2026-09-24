---
type: supplier
# Margin notes are cost data by design — see CONVENTIONS: Visibility.
visibility: admin
status: active
last_activity: 2026-09-24
---

# Triforest

**Rep / contact:** (not provided in today's ingest)
**Terms:** (not provided in today's ingest)
**Margin notes:** <!-- e.g. BIYORK near break-even, VIDAR volume trap -->

## Products carried
<!-- high level; live data stays in Airtable catalogue -->

## Log
- 2026-09-24 — created from Outlook daily ingest, top-level `needs_attention`: an email posing as Triforest Inc. ("Important Notice: Update to Triforest Inc. Banking Information") landed at info@ with a self-addressed To: field — a classic vendor-email-compromise (VEC) pattern. Titan has a real, active Triforest payment relationship (a $2,992.83 Interac e-transfer went out Sep 18, per the same run's admin roundup), which makes this a plausible targeted attack. **Do not update any banking/payment info from this email** — verify any change by phone using a known number first. No existing supplier note matched by name; created fresh (suppliers carry no source ID per the template). #admin
