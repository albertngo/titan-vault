---
type: process
visibility: admin
status: active
last_activity: 2026-10-22
---

# Finance process map (what actually happens today)

**Load this first in any session that touches money.** It is the one list of how
cash, sales and costs move through Titan right now, step by step, with what is
automated, what is manual, and what is not built. Platform quirks live in
[[QuickBooks]] and [[Lightspeed]]; procedure lives in titan-bookkeeper
`docs/financial-flow.md`; bank rules in `docs/consolidated-bank-rules.md`.
Update the step, date the change, never delete a step; strike it through and
say what replaced it.

## Money in

| # | Step | How it runs today | Status 2026-10-22 |
|---|---|---|---|
| 1 | Store sale rung in [[Lightspeed]], Right Register, Mississauga Outlet | Staff, daily | Working |
| 2 | Project payment arrives by Interac e-transfer to Albert, forwarded to BMO as `INTERAC ETRNSFR AD RECVD ALBERT NGO` | Albert, by hand | Working; the bank text never names the customer |
| 3 | Outlook e-transfer notice parsed into [[Notion]] Master Payments Log (sender, amount, date, project) | Make 4280466, 8 am daily | Working |
| 4 | Project sale rung in Lightspeed from the Master Payments Log "Input into LS" view, customer attached, tender E-Transfer | Albert, by hand | **Backlog.** None rung before 2026-10-21; catch-up in progress. Rule: full price when the subcontractor cost is in QBO, net 0 only when the cost is unknown |
| 5 | Register closure posts Invoice plus Payments by tender to QBO, into Undeposited Funds | Lightspeed to QBO integration, on closure | Working; posting date is the closure date |
| 6 | Register Closure Watchdog: WhatsApp plus Notion to-do if QBO has no invoices for 3 days | Make 4824368 | Built, **on-demand only, not scheduled**, 0 executions |
| 7 | Sale deposits in the BMO feed posted against Undeposited Funds (Categorize), never to Sales | Bank rules for Lightspeed payouts and e-transfers, set to Review | Rules written; **feeds broken** since early October (accountant, 2026-10-20), 206 deposits pending |
| 8 | Undeposited Funds reconciled by whole balance per month; merchant fees moved out by journal entry | Albert, monthly | **Not yet done.** Balance $189,428.94 on 2026-10-21; ~$47k standing residue unexplained |

## Money out

| # | Step | How it runs today | Status 2026-10-22 |
|---|---|---|---|
| 9 | Supplier invoices arrive by email; paid by e-transfer or bill payment | Albert / office, by hand | Working |
| 10 | Supplier payments coded in the feed: flooring and tile suppliers to Inventory Asset (HST on, Review); 3 vendor rules cover ~60 suppliers | Bank rules v3 | Working for known vendors; unknown e-transfers out stay manual |
| 11 | Subcontractor labour (GERARDO rule; Luxevista Construction not yet a rule) coded to Subcontractor expense, HST on | Bank rule plus manual | Working; add a Luxevista rule |
| 12 | Operating expenses auto-coded (subscriptions, vehicle, utilities, marketing, meals, insurance, bank fees, CRA, WSIB) | 30+ auto-add bank rules | Working. Trade-show signage should be Marketing, not Office Supplies; Vistaprint and Bannerbuzz rules need moving |
| 13 | `BPY/FAC` bill payments and large one-offs identified in BMO Payment History before coding | Manual | Working, no rule possible until the payee is known |
| 14 | Payroll via Intuit; feed lines land in Payroll Expenses for review; split needs the payroll register | Bank rule, Review | Working, manual split |
| 15 | Outlook invoices forwarded to QBO Receipts | Make 4841468 | Built, on-demand, 0 executions |

## Books and reporting

| # | Step | How it runs today | Status 2026-10-22 |
|---|---|---|---|
| 16 | A/R tracked in Lightspeed only; QBO A/R from Lightspeed nets to zero on arrival | By design | Working |
| 17 | Chart of accounts mirrored to a Make datastore (88653) | Make 4822446, 4824058 | Built, on-demand |
| 18 | P&L pulled to a datastore | Make 4822687 | Built, on-demand, 0 executions |
| 19 | Daily bookkeeper ingest to the agents pipeline | `bookkeeper-ingest-agent` | **Blocked** since 2026-07-26, no QuickBooks connector; Finance department blocked with it |
| 20 | HST remittance (GST-P rule) and filings; year-end | Accountant (Dang & Associates) | Working; accountant currently chasing the broken feeds |
| 21 | Monthly Lightspeed to QBO reconciliation | Nobody | **Not built.** Named as a playbook candidate in Project Status meetings; step 8 is its first version |

## Next to build or decide (in order)

1. Repair the BMO and TD feeds, then post the pending deposits against Undeposited Funds (step 7).
2. Finish the project e-transfer catch-up (step 4); confirm the cost-of-goods posting setting in Lightspeed first.
3. First whole-balance reconciliation and fee journal entry (step 8); explain the ~$47k residue with the accountant.
4. Rule fixes: Luxevista to Subcontractor; Vistaprint and Bannerbuzz to Marketing; add `Marketing:Trade Shows & Print`.
5. Schedule the Register Closure Watchdog (step 6) once closures are reliable.
6. A QuickBooks connector for the bookkeeper ingest (step 19), which unblocks Finance in the agents pipeline.

## Log
- 2026-10-22 — Created on Albert's instruction as the standing list to build on. #admin
