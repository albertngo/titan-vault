---
type: decision
visibility: admin
status: decided
date: 2026-09-29
---

# Product-image fill write_mode flipped plan_only → write

**Decision (Albert, in session, 2026-09-29):** `platform-settings/supplier-sites.json`
→ `write_mode.mode` changed from `"plan_only"` to `"write"` in
[[titan-agents-repo]]. `/image-fill` now attaches supplier product photos to the
Master Flooring Catalogue's **blank** `Swatch images`, `Room scene images` and
`Detail images` fields, plus a `Supplier product page` link, by policy
auto-approval (confident matches only), and reports what it holds.

Albert's words, after reviewing the Vidar pilot proof sheet: "1. go for it", and in
the same message "if the image is clearer or better, use it instead of the
floorbox. If it has more detail and room scenes; download them too." He had chosen
"Auto-attach, report held" for after the pilot earlier the same day.

**What was written first:** Vidar, 75 records: 69 swatches, 44 room scenes and
1 detail shot, from Speers Flooring (Shopify, brand named in its feed) and The Floor
Box (sitemap; brand inferred from import batches). 157 records held: 84 not listed
on either site, 68 whose only swatch is under 1600 px, 5 whose photo shows a
different laying pattern.

**Why the sources are retailers:** Vidar's own site answers automated readers with a
bot challenge, and the run does not work around one. Search-index links to Vidar's
product pages turned out dead (404), so `Supplier product page` holds the retailer
listing the photo came from (Albert's choice).

**Guards that stay:** blank fields only, checked again at write time; SKU never
written; one photo per field decided by the model looking at it; a record's own
width, grade and laying pattern must match the listing.

**Revisit when:** a wrong photo is found on a product, or Vidar supplies its own image
library (it would outrank both retailers).

**Addendum, same night — descriptive file names and one narrow replace.** Albert, on the
SEO/AEO question: "yes. Do all that you recommend and put it in the skill." Image files are
now named from the record's fields (`vidar-naked-oak-american-white-oak-engineered-hardwood-9in-select-swatch.jpg`;
the internal SKU is left out, the supplier's own code kept). Airtable's API ignores a new
filename on an existing attachment (tested on one record, nothing changed), so the 121
files already attached were **re-attached from the same source images under the new
names**. That is the one exception to "blank only, never replace" in the
`airtable_attach_images` contract (op `reattach_renamed`), and it applies only to a field
whose every file this pipeline named itself, checked against the live files first. All 75
records, 121 files, same byte sizes. Alt text and Product schema guidance for the website
are in bert-airtable-schema, "Product images".

Same session: 572 `Price List URL` values that vanished after 2026-09-28 (Vidar, Grandeur,
FAW records whose Supplier had been blank) were restored exactly as they were, blank fields
only, each link matched to its Notion Price Lists row (PL-367, 327, 293, 297, 377, 317,
231, 306, 353).

**Addendum, later that night — where photos and links come from.** Albert, starting BiYork:
"search the main website -> externals (floorbox and speers) but the link to the product url
page should be from the official company website; otherwise pick an the floorbox as the
backup. I would not want speers because it is a local shop to ours." So, for every supplier:
official site first, then The Floor Box, then Speers for photos; `Supplier product page` from
the official site, else The Floor Box, **never Speers**. This reverses the Speers-first order
Vidar was written with: 63 Vidar records currently link a Speers page (29 of them have a
Floor Box match). Whether to relink or clear those is open; nothing was changed. When the
environment refuses an official site, the run stops instead of letting retailers take the
blank fields first.
