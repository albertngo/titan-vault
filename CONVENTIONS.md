# titan-vault Conventions — v1.9

This vault is Titan Flooring's second brain. Humans and agents both write here.
This file is the contract: any agent writing to the vault reads it first, every run.

## Folder map

| Folder | Contains | Who writes |
|---|---|---|
| `01_daily/` | One note per day: `YYYY-MM-DD.md`. The distilled record of what happened. | vault-writer (overwrites on re-run) |
| `02_opportunities/` | One note per opportunity, matching the Titan Projects name where possible | vault-writer (Log section only) + Albert |
| `03_clients/` | One note per client: `Firstname Lastname.md` or `Company Name.md` | vault-writer (Log section only) + Albert |
| `04_goals/` | Quarterly and weekly goal notes. | Albert only (later: planner agent, proposals only) |
| `05_decisions/` | `YYYY-MM-DD-short-slug.md`. Explicit decisions only — never inferred. | vault-writer + Albert |
| `06_platforms/` | One reference note per platform (GHL, QBO, Airtable...): how Titan uses it, quirks, IDs. | Albert + agents **on explicit instruction only** — never as part of an automatic run |
| `07_suppliers/` | One note per supplier (BIYORK, VIDAR, Triforest, FAW, Purelux, Evergreen, GreenTouch, Olympia, CIF...) | vault-writer (Log section only) + Albert |
| `08_templates/` | Note templates below. | Nobody edits casually — templates are part of the contract. |
| `09_analyses/` | One note per analysis: `YYYY-MM-DD-slug.md`. The question, the distilled findings, and ID-joined wiki-links to every entity the analysis touched. Raw artifacts (CSV/JSON) stay in titan-agents; the vault keeps conclusions. | Albert + agents **on explicit instruction only** — never as part of an automatic run |

**During the build phase, read "vault-writer" in the Who-writes column as "Claude,
writing directly with Albert's go-ahead."** `vault-writer` is parked; see Agent access
below. The column describes the target routing, which is what the folder map is for —
only the writer differs today, never the rules.

## Scaling to more sources

The vault's job is to be a business overseer, not a mirror of every platform. That
comes from **breadth of sources feeding it, cross-linked**, not depth of records
per source — see note rule 4's earned-relevance clause. As QuickBooks, Notion,
email, or any other platform integrates, it follows the pattern GHL already set:

1. A `06_platforms/<Source>.md` reference note (quirks, IDs, how Titan uses it).
2. New source IDs on entity frontmatter alongside the existing ones —
   `qbo_customer_id`, `notion_page_id`, … — per the Identity rule (note rule 5).
3. Entity notes accumulate one Log line per source as things actually happen —
   never a bulk import of that source's full history on day one.

A client note that's picked up a GHL log line, then a QuickBooks invoice log line,
then a Notion meeting log line over time is the overseer working as intended. The
same client note pre-populated from a bulk pull of all three platforms on day one,
before any of that happened, is exactly the raw dump note rule 4 forbids.

## Note rules

1. **Frontmatter on every entity note** (03_clients/02_opportunities/07_suppliers):
   ```yaml
   ---
   type: client | opportunity | supplier
   status: active | prospect | complete | dormant
   last_activity: YYYY-MM-DD
   ---
   ```
2. **Entity notes have a `## Log` section.** Agents append dated bullets there and
   update frontmatter. Everything above the Log is human-owned prose — agents never rewrite it.
3. **Wiki-links everywhere.** Any mention of a client, opportunity, supplier, or platform
   in any note uses `[[Name]]`. Links are what make this a brain instead of a folder.
4. **No raw dumps.** The vault holds distilled knowledge — summaries, amounts, links
   back to the source platform. Full emails/transcripts stay in their platforms.

   **Earned relevance, not bulk import.** A client/opportunity/supplier note gets
   created when something durable happens to that entity — it wins, it lands in a
   daily-brief `needs_attention`, or an analysis touches it — never by a proactive
   bulk or windowed pull of a platform's history. The platform (queried live via
   MCP) is the source for anything not already noted; the vault only accumulates
   what's actually been decided or acted on. A note earned this way keeps
   collecting one Log line per source as things happen to it over time — that
   accretion, not import volume, is what makes the vault an overseer instead of a
   second CRM. (The 2026-07-26 two-month GHL backfill was originally
   grandfathered against this clause, then pruned to its earned-relevance
   survivors on 2026-07-28 on Albert's explicit instruction — see
   [[2026-07-28-prune-ghl-backfill]]. Deleted notes remain recoverable from git
   history at commit `c95e2a1`.)
5. **The Identity rule — source IDs are the join key.** Names are keys for humans;
   source IDs are keys for agents. One canonical name per entity for display and
   wiki-links. But every entity note created from ingest carries its source-system ID
   in frontmatter (`ghl_contact_id`, `ghl_opportunity_id`, …), and **agents match on
   the ID first, name second.**

   Why: names change and collide. "Jay" and "Jayanthan Kuhananthan" may be one person;
   a contact renamed in GHL would otherwise get a second note on the next run. The ID
   is the only stable identity, and it's what lets a note round-trip back to the source
   record or join against an ingest file or analysis CSV.

   - Source ID is REQUIRED on ingest-created entity notes. If the record genuinely has
     none, say so (`ghl_contact_id: none — phone-only contact`) rather than leaving it
     silently blank; a blank field is indistinguishable from a bug.
   - Never overwrite an existing ID. A different ID on a same-named entity means two
     records — flag as a possible duplicate, never merge.
   - Suspected duplicates get flagged in the daily note, resolved by Albert, never
     auto-merged.
   - Which IDs go on which note type — the templates are the authority, and this list
     must match them: `ghl_contact_id` + `ghl_conversation_ids[]` on clients;
     `ghl_opportunity_id` + `ghl_contact_id` + `ghl_pipeline` + `ghl_stage` on
     opportunities. Ingest records carry these on every record that has one — propagate
     them, don't drop them. Pipeline and stage are **names, not IDs**: stage IDs are
     opaque and get renamed in the GHL UI, so the name is what a human can verify.

   **This section is the single source of truth for entity identity.** Agent
   definitions in titan-agents cite it by name rather than restating it, so the rule
   changes in one place. A restated copy is a copy that will drift.
6. **Append, don't rewrite.** History is the point. Corrections are new dated entries.

## Agent access

**Build phase (current).** `vault-writer` is **parked** — see its definition in
titan-agents. Claude writes here directly instead, one change at a time, with Albert's
go-ahead on each. Every rule in this file still applies; only the routing differs.

**Current shape.** `vault-writer` is un-parked (2026-07-27) and wired into
`/daily-ingest` on the titan-agents side — it is the agent making these commits now,
limited to the patterns in its own definition. All other agents remain read-only.

- Every agent write session ends with a git commit: `vault: <what> YYYY-MM-DD`.
- Vault commits go to `main-vault` (this repo's actual default branch) — no review step.

## Versioning

- **v1.9** (2026-07-28) — Reversed v1.7's grandfather carve-out on Albert's
  explicit instruction: the 2026-07-26 two-month GHL backfill was pruned to its
  earned-relevance survivors (522 of 598 notes deleted; kept: won cohort,
  analysis-referenced, daily-brief-touched — see
  [[2026-07-28-prune-ghl-backfill]]). Correction recorded while doing so:
  v1.7's "297 won-opportunity notes" were never written to the vault — the 297
  wins live as `won_records` in the titan-agents repo; only 15 won-opportunity
  notes existed here, all kept. The earned-relevance clause itself is unchanged
  and now applies without exception. No template or folder changes.
- **v1.8** (2026-07-27) — `vault-writer` un-parked, wired into `/daily-ingest`,
  bound strictly to its existing whitelist. Its first real run committed
  `ee2da90` (5 new entity notes, 11 Log-append updates, 1 daily note — see
  titan-agents-repo `ingest/2026-07-27/`). Also corrected the push-target
  branch name from `main` to `main-vault` (this repo's actual default branch,
  confirmed with Albert 2026-07-27 — the earlier `main` references were always
  wrong, not a rename). No folder, template, or frontmatter changes.

Bump this file's version and note the migration when structure changes.
Agents must refuse to write if they can't find this file.

- **v1.7** (2026-07-26) — Added the "Scaling to more sources" section and note
  rule 4's "Earned relevance, not bulk import" clause, after a full-history GHL
  backfill (1,958 opportunities + contacts) was proposed and reconsidered
  mid-pull. The vault's overseer ambition — ingesting accounting, Notion, email,
  and more alongside GHL — comes from breadth of cross-linked sources per entity,
  not from mirroring each source's full history. A note is earned (wins, hits a
  daily-brief `needs_attention`, or gets touched by an analysis) and then
  accumulates one Log line per source over time; it is never bulk-imported on
  day one. The existing 2026-07-26 two-month GHL window and the 297
  won-opportunity notes predate this clause and are explicitly grandfathered —
  no retroactive pruning. No template or folder changes.
- **v1.6** (2026-07-26) — Client and opportunity templates gained
  `ghl_assigned_to` (name) + `ghl_assigned_to_id` (GHL user id): the current
  assigned user, kept to decide whom the next task goes to. **Operational data,
  not identity** — it is NOT part of the Identity rule's join keys and may change
  on any sync; agents still match records on the entity IDs alone. Absent fields
  mean unassigned in GHL (or no assignment data in the sync that wrote the note).
  Backfilled across existing notes at bump time (309 clients, 246 opportunities).
- **v1.5** (2026-07-26) — Added `09_analyses/` and `templates/analysis.md`. Analyses
  previously had no home: titan-agents' CLAUDE.md said findings worth keeping go to
  the vault but named no folder, and `05_decisions/` (explicit decisions only) and
  `01_daily/` (the day's record) both refuse them. One note per analysis,
  `YYYY-MM-DD-slug.md`: the question asked, distilled findings (note rule 4 — tables
  of results, never row dumps), a **Related** section of wiki-links produced by
  ID-joining the analysis output against entity notes (note rule 5), and a pointer
  back to the raw artifact in titan-agents, which stays the system of record for
  data. Entity notes are NOT edited per-analysis — backlinks carry the connection;
  a finding that changes how one client is treated is a dated Log append on that one
  note. Write access mirrors `06_platforms/`: explicit instruction only. No
  migration — no analysis notes existed at bump time.
- **v1.4** (2026-07-26) — Numbered every top-level folder to fix the intended reading/
  processing order in a plain file listing: `01_daily/` `02_opportunities/`
  `03_clients/` `04_goals/` `05_decisions/` `06_platforms/` `07_suppliers/`
  `08_templates/`. Folder map table reordered to match. Purely a rename — no content,
  ownership, or rule changes. Earlier changelog entries below keep their original
  (unprefixed) folder names since that's what was true at the time; read historically.
- **v1.3** (2026-07-26) — Renamed the `projects/` folder to `opportunities/` (and
  `type: project` to `type: opportunity`) to match GHL's own terminology
  (`ghl_opportunity_id`, the Sales Pipeline of opportunities) rather than running a
  second, unrelated word for the same thing. `templates/project.md` renamed to
  `templates/opportunity.md`; the `## Projects` section on client/supplier notes
  renamed to `## Opportunities`. GHL's own literal terms (the "Project Won" pipeline
  stage, the "project complete" tag) are untouched — those are the platform's
  vocabulary, not the vault's. No existing opportunity-type notes required migration;
  none existed at rename time.
- **v1.2** (2026-07-25) — Note rule 5 named the **Identity rule** and made the single
  source of truth for entity identity. It absorbs the per-note-type ID field mapping
  that `vault-writer` used to restate; that agent and `ghl-ingest` now cite this
  section instead of carrying their own copies. Also in this pass: `platforms/`
  ownership sharpened to "on explicit instruction only", resolving a standing
  contradiction with `vault-writer`'s whitelist; a build-phase note added to the
  folder map so the Who-writes column isn't read as live routing while `vault-writer`
  is parked. No folder, template, or frontmatter changes — the ID mapping was
  transcribed from the existing templates, not imposed on them, so nothing in the
  vault needs rewriting. Migration is reference-only, on the titan-agents side.
- **v1.1** (2026-07-25) — Agent access rewritten: `vault-writer` parked for the build
  phase, direct Claude writes in its place, `main` named as the push target. Folder map
  and note rules unchanged.
