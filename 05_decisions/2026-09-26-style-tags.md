---
type: decision
visibility: admin
status: decided
date: 2026-09-26
---

# Style tags: AI-suggested design layer on the catalogue, built plan_only

**Decision (Albert, in session, 2026-09-26):** build `/style-tag` in
[[titan-agents-repo]] — AI-suggested `Undertone`, `Tone depth`, `Texture`, `Style`
and `Busyness` on Master Flooring Catalogue records, blank fields only, marked
`AI suggested` for staff to confirm — and take every recommendation in the plan
(`methods/style-tags.md`, D1–D6):

- One standing Notion row per supplier in the Price Lists database carries the
  troubled report (`Troubled Files` + the page table with the `Action` column).
- v1 is flooring only; Tile / Stone waits for its own texture table.
- The report is its own contract (`troubled-tags-1`), one row per SKU × field.
- `Style` on a record with no image is held, never written from specs alone.
- A reviewer's `Action` answer writes the tag as `AI suggested`; the run never
  writes `Staff confirmed`.
- The session model reads the images and writes a judgement file; a script decides.

Same day, Albert split the image field: `Images` became **`Swatch images`** (same
id) and **`Room scene images`** and **`Detail images`** were added, with the rule
*"Colour tags come from Swatch images only; never from Room scene images. Style
uses swatch + room scenes. Texture uses specs + Detail images. No swatch → hold
colour tags."* That rule is structural in the build: an image's kind is the field
it sits in, and a room scene cannot reach the colour tags at any confidence.

**Why:** the design layer is what the future recommendation layer (the `Design
Rules` table) keys on, and 8,253 records have none of it. Specs already decide
Texture and Busyness deterministically for ~1,575 active flooring records; the
colour tags wait on swatches. Marking suggestions rather than asserting them, and
never touching a `Staff confirmed` record, is what makes it safe to fill at scale.

**What is held back:** `write_mode` is `plan_only`. The first runs produce the
plan, the troubled CSV and the Notion report with no Airtable write. Flipping to
`write` is its own dated decision, like [[2026-09-14-social-write-mode-live]].

**Alternatives considered:** a separate "Style Tag Runs" Notion database (cleaner
filters, more machinery — later if runs become frequent); a Claude API script for
the image reads (needs a new credential; the scale path); reusing the 12-column
price-list troubled file (wrong unit — a SKU, not a SKU × field).

**Blockers still live:** no record carries an image yet; the cloud environment's
proxy refuses the Airtable attachment host (`v5.airtableusercontent.com`), so image
runs need that host allowed or Albert's Mac; HEIC originals cannot be decoded
without `pillow-heif`.

**Revisit when:** the first `plan_only` run on one supplier has been read
(flip `write_mode`); a few hundred `Staff confirmed` records exist (calibrate the
0.7 threshold and the rule tables against what staff kept); Tile / Stone is asked
for; the EIR and `BCDE` rulings in `methods/style-tags.md` §15 are answered.

## Related
- [[titan-agents-repo]] `methods/style-tags.md`, `contracts/style-plan-schema.md`,
  `contracts/troubled-tags-schema.md`, `platform-settings/style-tags.json`
- [[2026-09-14-social-write-mode-live]] — the same staged-rollout shape
