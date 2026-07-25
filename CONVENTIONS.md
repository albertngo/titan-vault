# titan-vault Conventions — v2

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
   Client notes carry an additional identity block — see rule 5.
2. **Entity notes have a `## Log` section.** Agents append dated bullets there and
   update frontmatter. Everything above the Log is human-owned prose — agents never rewrite it.
3. **Wiki-links everywhere.** Any mention of a client, project, supplier, or platform
   in any note uses `[[Name]]`. Links are what make this a brain instead of a folder.
4. **No raw dumps.** The vault holds distilled knowledge — summaries, amounts, links
   back to the source platform. Full emails/transcripts stay in their platforms.
5. **Names are labels; IDs are keys.** The filename stays the human-readable canonical
   name — that's what makes `[[Wiki Links]]` worth having, and it never becomes a UUID.
   But the name is not what identifies the person. Client notes carry an identity block
   in frontmatter:

   ```yaml
   ghl_contact_id: # canonical key — GHL contact UUID. Set by ingest, never by hand.
   phone: "+14165551234"  # E.164, ALWAYS quoted
   email:
   aliases: []     # other spellings / short forms seen in GHL, e.g. ["Jay"]
   ```

   ⚠️ **Quote the phone number.** Unquoted, `+14165551234` parses as the integer
   `14165551234` and the `+` is silently lost — which breaks E.164 matching in exactly
   the place it matters. Same applies anywhere else a `+`-prefixed value enters YAML.

   - `ghl_contact_id` is **the** join key. [[GHL]] is where a client first exists, its
     IDs are stable across renames, and every other system (Airtable, QBO) is
     downstream of a deal that started there.
   - Matching precedence for agents: `ghl_contact_id` → `phone` → `email` → name.
     Never match on name alone when an ID is present.
   - `aliases` is how short forms and misspellings resolve to one note without
     renaming anything. Adding an alias is not a merge.
   - Suspected duplicates get flagged in the daily note, resolved by Albert, never
     auto-merged. An alias Albert hasn't confirmed stays commented as unconfirmed.
   - A client with no `ghl_contact_id` is a known gap, not a normal state: ingest
     backfills it on the next run that touches the contact.
6. **Append, don't rewrite.** History is the point. Corrections are new dated entries.

## Agent access

- `vault-writer` (in titan-agents) is the only agent with write access, limited to
  the patterns in its own definition. All other agents read-only.
- Every agent write session ends with a git commit: `vault: daily update YYYY-MM-DD`.

## Versioning

Bump this file's version and note the migration when structure changes.
Agents must refuse to write if they can't find this file.

- **v2 (2026-07-25)** — Rule 5 rewritten: client notes gain a frontmatter identity
  block (`ghl_contact_id`, `phone`, `email`, `aliases`) and agents match on ID before
  name. `templates/client.md` updated; the 8 existing client notes carry the block with
  `ghl_contact_id` as a TODO pending an ingest run. Projects and suppliers are unchanged
  in v2 — see the open question below.
- **Open (v3 candidate):** projects have the same weakness — `projects/` notes are keyed
  by name and link to Airtable only as prose in **Links:**. An `airtable_record_id` field
  would close it. Not done yet: Albert to confirm whether the Titan Projects record ID or
  the GHL opportunity ID is the better key for a project.
