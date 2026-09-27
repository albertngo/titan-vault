---
type: decision
visibility: admin
status: decided
date: 2026-09-26
---

# Style tags write_mode flipped plan_only → write

**Decision (Albert, in session, 2026-09-26):** in [[titan-agents-repo]], `platform-settings/style-tags.json` → `write_mode.mode` changed from `"plan_only"` to `"write"`.

`/style-tag` now writes approved style tags to the Master Flooring Catalogue in Airtable:
- only into blank fields;
- marked `AI suggested`;
- never on a `Staff confirmed` record.

The registry's `_flip` note asked for this to be a dated decision recorded here. This note is that record.

**Why:** the first spot run (PURELUX, 4 Journey SKUs: LVP-PLUX-0043/0048/0051/0052) ran as plan_only. Its only visible output was the Notion review row "Style tags — PURELUX". Albert's response was "The style tags should be in AIRTABLE, not notion". Offered three options, he chose "Write the 10": write the tags that cleared `min_confidence` 0.7, and leave held rows unwritten.

**What was written:** 10 tags (Undertone ×3, Tone depth ×4, Style ×3) across the 4 records. They were read back and verified; nothing was dropped or refused. Evidence: titan-agents PR #62, `ingest/2026-09-26/actions-log.json`.

**What stays gated:**
- **Held rows are not written.** Ten held rows stay on the Notion review row for Albert to answer in its `Action` column:
  - Texture on the open EIR ruling;
  - Busyness, since Journey has no Grade;
  - Westgate's low-confidence Undertone and Style.
- **The approval file is still required.** Every write still needs an approval file naming its exact `sty-` ids.
- **Staff confirmation stays with staff.** `Staff confirmed` is only ever set by staff in Airtable.

**Scope:** this is a global switch for every future `/style-tag` run on every supplier, not a one-run override.

**Revisit when:** staff find a wrong tag that was written at or above 0.7. The response then is to raise `min_confidence` or tighten the rubric or rule table, not only to fix the one record. The calibration analysis in `methods/style-tags.md` §10 step 6 is the planned check once a few hundred records are `Staff confirmed`.

## Related
<!-- [[2026-09-14-social-write-mode-live]] -->
