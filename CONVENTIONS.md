# titan-vault Conventions — v1.2

This vault is Titan Flooring's second brain. Humans and agents both write here.
This file is the contract: any agent writing to the vault reads it first, every run.

## Folder map

| Folder | Contains | Who writes |
|---|---|---|
| `daily/` | One note per day: `YYYY-MM-DD.md`. The distilled record of what happened. | vault-writer (overwrites on re-run) |
| `clients/` | One note per client: `Firstname Lastname.md` or `Company Name.md` | vault-writer (Log section only) + Albert |
| `projects/` | One note per project, matching the Titan Projects name where possible | vault-writer (Log section only) + Albert |
| `suppliers/` | One note per supplier (BIYORK, VIDAR, Triforest, FAW, Purelux, Evergreen, GreenTouch, Olympia, CIF...) | vault-writer (Log section only) + Albert |
| `decisions/` | `YYYY-MM-DD-short-slug.md`. Explicit decisions only — never inferred. | vault-writer + Albert |
| `goals/` | Quarterly and weekly goal notes. | Albert only (later: planner agent, proposals only) |
| `platforms/` | One reference note per platform (GHL, QBO, Airtable...): how Titan uses it, quirks, IDs. | Albert + agents **on explicit instruction only** — never as part of an automatic run |
| `templates/` | Note templates below. | Nobody edits casually — templates are part of the contract. |

**During the build phase, read "vault-writer" in the Who-writes column as "Claude,
writing directly with Albert's go-ahead."** `vault-writer` is parked; see Agent access
below. The column describes the target routing, which is what the folder map is for —
only the writer differs today, never the rules.

## Note rules

1. **Frontmatter on every entity note** (clients/projects/suppliers):
   ```yaml
   ---
   type: client | project | supplier
   status: active | prospect | complete | dormant
   last_activity: YYYY-MM-DD
   ---
   ```
2. **Entity notes have a `## Log` section.** Agents append dated bullets there and
   update frontmatter. Everything above the Log is human-owned prose — agents never rewrite it.
3. **Wiki-links everywhere.** Any mention of a client, project, supplier, or platform
   in any note uses `[[Name]]`. Links are what make this a brain instead of a folder.
4. **No raw dumps.** The vault holds distilled knowledge — summaries, amounts, links
   back to the source platform. Full emails/transcripts stay in their platforms.
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
     projects. Ingest records carry these on every record that has one — propagate
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

**Target shape.** `vault-writer` becomes the only agent with write access, limited to
the patterns in its own definition, all other agents read-only. Un-park it once the
agent architecture and the ingest contracts have settled — its whitelist enumerates
folders and contracts, so spec'ing it against a moving target means rewriting it on
every change.

- Every agent write session ends with a git commit: `vault: <what> YYYY-MM-DD`.
- Vault commits go to `main` — no review step.

## Versioning

Bump this file's version and note the migration when structure changes.
Agents must refuse to write if they can't find this file.

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
