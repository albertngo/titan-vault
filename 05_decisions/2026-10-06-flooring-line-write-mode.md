---
type: decision
visibility: admin
status: decided
date: 2026-10-06
---

# Payout flow: flooring lines write; rates are pre-tax

**Decision (Albert, in session, 2026-10-06):** `/project-costs-sync` in
[[titan-agents-repo]] may now **write** Flooring Line Items: create a line for each
flooring product ordered for a project, and update its cost as the supplier's
confirmation, invoice and credit memos arrive. Set in `platform-settings/payout-policy.json`
→ `write_mode.project_costs_sync_kinds.flooring_line = "write"`. Every other sync
action (NFM cost, disposal cost, payment links, Costs Complete, paid stamps) stays
`plan_only` until its own decision.

Albert's words: "1. Pretax flooring line item rates  2. Writing flooring line items is ok
3. Ok I'll schedule it soon  4. Leave those alone".

**What a flooring line now holds:**
- `Cost Rate`: the actual pre-tax $/sqft paid. Supplier invoice net of credit memos
  once it lands (restocking fees included, spread over the sqft kept), which ticks
  `Cost Locked`. Before that, the supplier confirmation, else the Lightspeed PO.
- `Sold At Rate`: the PM's `Quote Rate`, never the Lightspeed sale price.
- Named `<SKU>_<colour>` after the **ordered** product. A Lightspeed sale keyed with a
  different product is flagged as a PM entry mistake (PP-461: sold Click 5", ordered
  6" T&G).

**Pre-tax** matches the Data Entry Cheat Sheet (the formulas add HST) and the rows
staff already enter (PP-449 `SPC-VIDR-0002_Yukon` at $1.59, Vidar's pre-tax price).
The Notion descriptions on `Cost Rate` / `Sold At Rate` still say "including tax".

**Left alone:** the PP-421 / PP-399 Disposal rows, whose costs look swapped against AP
Disposal invoices 2388 / 2389 (both jobs predate the September scope).

**Revisit when:** a flooring line's cost is found wrong after the invoice, or a second
supplier's documents are added (only Vidar is read today).
