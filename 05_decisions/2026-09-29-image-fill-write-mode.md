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
