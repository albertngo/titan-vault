# titan-vault Conventions — v1

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
| `platforms/` | One reference note per platform (GHL, QBO, Airtable...): how Titan uses it, quirks, IDs. | Albert + agents on request |
| `templates/` | Note templates below. | Nobody edits casually — templates are part of the contract. |

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
5. **Names are keys.** One canonical name per entity. Suspected duplicates get flagged
   in the daily note, resolved by Albert, never auto-merged.
6. **Append, don't rewrite.** History is the point. Corrections are new dated entries.

## Agent access

- `vault-writer` (in titan-agents) is the only agent with write access, limited to
  the patterns in its own definition. All other agents read-only.
- Every agent write session ends with a git commit: `vault: daily update YYYY-MM-DD`.

## Versioning

Bump this file's version and note the migration when structure changes.
Agents must refuse to write if they can't find this file.
