---
type: decision
visibility: admin
status: decided
date: 2026-09-12
---

# Retire WordPress; rebuild titanfloors.ca as Next.js with an Airtable projection

**Decision:** Retire WordPress/Elementor entirely (not headless). Rebuild as Next.js
on Vercel — the front-end choice Albert made in an earlier conversation, recorded here
since no decision note existed for it before today — with content as MDX files in a new
`titan-web` repo and the product catalogue served from a read-only, whitelisted
projection out of Airtable's Master Flooring Catalogue. The site never reads Airtable or
Lightspeed live. **Phase 1 shows no SKU-level prices.**

**Why:** The live site turned out smaller and more disposable than the earlier
headless-WordPress plan assumed — of ~147 published pages, ~120 are one LPagery
"{service} × {city}" template across ~20 cities, plus ~10 leftover theme-demo pages;
WooCommerce is active but dead (zero orders, zero customers, ever). The real content is
~133 blog posts and ~15 real pages. Keeping WordPress "because the content's already
there" didn't hold once the site was actually inventoried.

Governance/security trend for WordPress is negative: Patchstack logged +42% YoY
vulnerabilities across the ecosystem in 2025, 91% of them in plugins; on 2026-09-09
Automattic's board put its own CEO on leave over the ongoing WP Engine lawsuit — by
09-11 he said he was back in control, unresolved as of writing.

**The no-prices rule has a specific cause, not just caution:** the titan-agents-repo is
public and publishes the exact markup formula (`Retail = Cost + $1.00`) plus
per-supplier cost multipliers ([[GHL]]'s sibling repo — see
`titan-agents-repo/.claude/skills/bert-airtable-schema/SKILL.md`). A synced SKU-level
price on the website would let any competing dealer back out Titan's cost from every
supplier's line. The current quote-request model (pick flooring, send the SKUs) is kept
and built out properly — a real product finder, a sq-ft/box calculator, a wishlist that
becomes a quote request — rather than replaced with a public price list.

Sales data points the same direction on scope: booked appointments convert far better
than anything else, in-store/in-home visits close noticeably larger deals, and the
retail-material (STORE) pipeline is a small fraction of revenue next to project work —
see [[2026-07-29-lead-funnel]] and [[2026-07-26-won-analysis]]. This is a booking-led
business; full ecommerce is not what the site needs to do right now.

**Alternatives considered:**
- *Stay on WordPress/Elementor, clean it up.* Legitimate if being able to log into a
  dashboard and click "edit page" matters more than everything else — a real trade-off,
  not a wrong choice, if that's the priority.
- *Headless WordPress + Next.js* (the earlier plan). Rejected: still runs the entire
  plugin stack to render REST bodies, still needs SiteGround, still carries the dead
  WooCommerce install, unchanged attack surface — for a migration that turns out to be
  small anyway.
- *Elementor MCP as the editing path.* Rejected: Elementor's own MCP guidance is thin;
  the capable servers are third-party; building on Elementor's JSON blobs is the
  opposite of the portable, file-based content this rebuild is meant to produce.
- *Shopify as the whole site.* Rejected for now — ecommerce-first for a business with
  zero online orders to date. Revisit if retail-online becomes the actual strategy;
  Lightspeed X-Series ships a first-party Shopify connector and Shopify's Storefront
  MCP/UCP would put the catalogue in front of AI answer engines, which is a real reason
  to prefer it over WooCommerce whenever full ecommerce does arrive.

**Revisit when:**
- Retail-online sales become a real strategy → reopen Shopify (phase 2).
- A non-technical editor is needed → add Keystatic (git-backed editor, no architecture
  change, additive only).
- Prices go on the site → needs a `Web price` field driven by a markup not present in
  the public repo, or the repo itself goes private. Needs the per-supplier
  MAP-vs-MSRP semantics resolved first (`MAP price ($/sf)` currently holds either a
  real floor or a plain list price with no flag to tell which).
- The Meta Ads landing page's destination URL — captured before cutover so ad
  attribution survives it.

## Related
[[GHL]] · [[2026-07-29-lead-funnel]] · [[2026-07-26-won-analysis]]

Full write-up: `titan-agents-repo: methods/website-architecture.md`.
Site inventory and redirect map: `titan-agents-repo: analysis/output/website-inventory-2026-09-12.json`,
`analysis/output/website-redirects-2026-09-12.csv`.

Two open items tracked separately from this decision: two Make.com scenarios feeding
the current site's forms have been erroring for weeks while still running (possible
silent lead loss, independent of the rebuild); and Search Console access could not be
read through this session's WordPress connection, so the city-page keep/consolidate
call still needs a manual export from Albert's Google account.
