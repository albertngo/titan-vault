---
type: platform
visibility: admin
status: active
last_activity: 2026-10-21
---

# Lightspeed Retail (X-Series)

Titan's POS, **the sale of record and the A/R.** Every sale, store or project,
is rung here and nowhere else. Outlet "Mississauga Outlet", register "Right
Register". Payment types: Cash, Cash VA, Cash rounding, Cheque, E-Transfer,
Lightspeed Payments, Loyalty.

Two roles in titan-agents, kept separate:

- **Catalogue** (products, pricing, variants): written only by
  `scripts/lightspeed_write.py` and `scripts/lightspeed_push.py` through
  `/catalog-sync`; ids in `platform-settings/lightspeed.json`. Not covered here.
- **Sales to the books:** the QuickBooks Online integration, below. No agent
  reads sales today.

## What the register closure does

Closing the register is the trigger for everything downstream. Lightspeed posts
each closure to [[QuickBooks]] as an Invoice plus Payments grouped by tender
type into Undeposited Funds; customer-attached sales post under the customer.
Posting date is the closure date, not the sale date. An unclosed register means
no sales in QBO, which is what the Make Register Closure Watchdog (4824368)
nags about.

Close with the counted fields filled in. A closure counted at $0.00 posts the
same amounts to QBO but records a full shortage in Lightspeed's own reports
(happened 2026-10-21).

## Project e-transfers

Project payments arrive by e-transfer and are logged in [[Notion]]'s Master
Payments Log by Make; the "Input into LS" view is the list not yet rung.
Decision 2026-10-21: ring each as one sale on a non-inventory project item,
tender E-Transfer, at net 0 inside Lightspeed (cost equal to price), **provided
the QBO integration does not post cost of goods**; if it does, cost must be $0.
Procedure: titan-bookkeeper `docs/financial-flow.md`, section 5.

## Open

- Whether the QBO integration posts cost of goods / inventory journals
  (Setup > Apps > QuickBooks Online). Unchecked as of 2026-10-21.
- The 2026-10-21 closure's two large register lines in QBO ($7,765.40 and
  $5,438.85) did not tie to the closure screen's Cash and Lightspeed Payments
  totals. Open one payment in QBO to see which invoice it paid.

## Log
- 2026-10-21 — Note created on Albert's instruction, alongside [[QuickBooks]].
  Sales-side only; the catalogue side has lived in titan-agents since the
  pipeline was built. #admin
