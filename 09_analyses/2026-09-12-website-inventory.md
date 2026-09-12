---
type: analysis
visibility: admin
date: 2026-09-12
question: What does titanfloors.ca actually contain today, and which of its URLs need a redirect when it's rebuilt?
sources: [WordPress (titanfloors.ca, via WP Agent connector), "titan-agents: analysis/output/website-inventory-2026-09-12.json", "titan-agents: analysis/output/website-redirects-2026-09-12.csv"]
---

# Website inventory — titanfloors.ca, 2026-09-12

**Question:** What does the live WordPress site actually contain, and which of its
pages need a real redirect rule versus simply keeping their own URL when the site is
rebuilt?

**Answer:** The site holds far less real content than its 147-page count suggests —
120 of those pages are one programmatic city-page template, and a dead WooCommerce
store (zero orders, zero customers, ever) accounts for another 179 catalogue-style
entries that need to point at the new catalogue rather than migrate as-is. Only 28
URLs need an actual redirect rule; the other 127 non-WooCommerce pages keep their own
address, pending a Search Console review to confirm which programmatic city pages are
worth keeping at all.

## Findings

| | Count |
|---|---|
| Published pages | 147 (146 real + 1 draft) |
| Of which: programmatic "{service} × {city}" pages | ~120, one LPagery template across ~20 cities |
| Of which: leftover theme-demo pages | ~13 (never real content, e.g. `/furniture-04-2/`, `/cart-2/`, `/wishlist1/`) |
| Published blog posts | ~133 |
| WooCommerce products | 179 (verified: category counts sum exactly — Laminate 56, Mosaic 53, Engineered 39, Vinyl 16, Solid 15) |
| WooCommerce orders / customers, ever | 0 / 0 |
| Redirect actions actually needed | 28 |
| Pages that keep their own URL (pending GSC review) | 127 |

**The 28 real redirects, by type:**
- 2 slug typos (`lamiante-flooring-mississauga`, `vinyl_flooring_oakville`)
- 1 wrong-parent defect (a vinyl-flooring page filed under `/stair-refinishing/`)
- 13 leftover theme-demo pages → home
- 7 WooCommerce category pages → the new catalogue's category pages
- All ~179 WooCommerce product pages → the new catalogue root (no reliable
  product-to-product mapping exists — WooCommerce's SKUs, like `TF1122-F`, don't match
  Airtable's `CAT-SUPP-0001` scheme)

**A defect worth fixing regardless of the rebuild:** the contact page's map embed still
shows the old 991 Matheson Blvd East address; the page's own text already has the
correct one, 1060 Britannia Rd East #2.

**What still needs a human:** Search Console access could not be read through this
session's WordPress connection (a Google-session OAuth scope this connector doesn't
carry), so the 127 kept-as-is pages — six of which are Mississauga neighbourhoods
(Erin Mills, Meadowvale, Clarkson, Port Credit, Streetsville, Malton) competing with
Mississauga's own page — all default to "keep." A 16-month Search Console export would
let the redirect map fold low-traffic neighbourhood pages into their parent city
instead.

## Related
No client, opportunity, or supplier notes touched by this analysis.

## Source data
`titan-agents-repo: analysis/website_inventory.py` (the read-only crawl script — network
to titanfloors.ca is blocked from the sandbox this session ran in, so this inventory was
assembled by hand from the WP Agent connector's output instead; the script is ready for
a machine-verified re-run once network access exists). Full data:
`titan-agents-repo: analysis/output/website-inventory-2026-09-12.json` and
`website-redirects-2026-09-12.csv`. Feeds the decision at
[[2026-09-12-website-architecture]].
