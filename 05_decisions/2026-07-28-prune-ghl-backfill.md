---
type: decision
status: decided
date: 2026-07-28
---

# Prune the 2026-07-26 GHL backfill to its earned-relevance survivors

**Decision (Albert, 2026-07-28):** delete every note created by the two-month
GHL backfill (`c95e2a1`, 598 notes: 263 opportunities + 335 clients) that never
earned its place — keeping only notes that were (a) touched by a daily-brief
run since, (b) part of the won cohort, or (c) wikilink-referenced from an
analysis or daily note. This reverses v1.7's explicit grandfather carve-out
("no retroactive pruning"); CONVENTIONS.md is bumped to v1.9 recording the
reversal. Rationale: the vault should be the refined, daily-maintained layer —
raw lead mass belongs in GHL (queryable live) and in the titan-agents repo's
derived tables, not as hundreds of never-touched stubs.

## What was deleted — 522 of 598

- 224 opportunities: ~133 abandoned, ~9 lost, ~92 open-but-never-touched
- 298 clients: prospect stubs, many phone-number-titled with empty Context
- Includes 2 accented-name notes (Rosiè Moncé pair) missed by the first audit
  pass (git quotes non-ASCII paths; parser skipped them — caught on live recount)

## What was kept — 76 backfill notes + everything non-backfill

- 31 backfill notes organically modified by daily-brief runs (plus 21 created
  fresh after the backfill, which were never candidates)
- All 15 won opportunities (`status: complete`) + their 8 client notes — every
  one is wikilinked from [[2026-07-26-won-analysis]]
- 22 further notes wikilinked from daily notes (e.g. [[Jly]], [[Dree Basant]],
  [[Jason C]], [[Charles Crooks]]) — a brief *mentioned* them without writing
  to them; deleting would have broken live links

Selection trap worth remembering: `b03ceed` (v1.6 frontmatter backfill)
mechanically touched 555 of the 598 — any "modified since import" test must
exclude it, or nearly everything looks earned. And two wins sit at stage
`*Meeting (Scheduled)*` despite `status: complete` — filter on status, never
stage.

## Corrections recorded

- v1.7's changelog claimed "297 won-opportunity notes" were grandfathered.
  They never existed in the vault — the 297 wins live as `won_records.json` /
  `won_rows.csv` in the titan-agents repo. Only 15 won-opportunity notes were
  ever written here; all 15 survive.

## Recovery

Nothing is unrecoverable. Any deleted note: `git checkout c95e2a1 -- "<path>"`.
Full list of the 522 paths: `git show --name-status <prune commit>` on
`main-vault`.
