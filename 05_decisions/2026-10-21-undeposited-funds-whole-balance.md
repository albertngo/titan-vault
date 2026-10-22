---
type: decision
visibility: admin
date: 2026-10-21
status: decided
---

# Undeposited Funds is reconciled by whole balance, and project e-transfers are rung in Lightspeed

**Decision:** Three parts, all Albert, 2026-10-21.

1. Every bank deposit that came from a Lightspeed sale is posted against
   Undeposited Funds (Categorize, Match, or Transfer, which are the same entry),
   never to Sales. Lightspeed's invoice is the only place revenue is recorded.
2. Undeposited Funds is reconciled **by whole balance**, period by period, not
   line by line. QBO's Match offers are optional hints. The control is:
   Lightspeed closure totals by tender for the month equal deposits posted
   against Undeposited Funds that month, plus merchant fees, plus cash on hand
   and card batches in transit.
3. The backlog of project e-transfers (Notion Master Payments Log, "Input into
   LS" view) is rung in Lightspeed, one sale per transfer, tender E-Transfer,
   at net 0 inside Lightspeed. Only after a sale is rung is its deposit posted
   against Undeposited Funds.

**Why:** The double count happens exactly one way: a sale posts to QBO through
Lightspeed, and then its deposit is also categorized as income. Fixing the
deposit side to Undeposited Funds removes that path. Line-level matching was
rejected because Lightspeed groups payments by tender per closure while the
bank shows individual transfers, so exact matches are rare and the balance is
what matters anyway. A/R is not tracked in QBO; Lightspeed is the A/R.

**Alternatives considered:**
- Switching off the Lightspeed to QBO sync and recording revenue from bank
  deposits. Rejected: loses HST accuracy, fees and timing; breaks the
  Register Closure Watchdog.
- Mapping the E-Transfer payment type straight to BMO instead of Undeposited
  Funds so the feed can Match directly. Deferred: works for customer-attached
  sales, fails for register summaries, and a missed Match doubles the bank
  register.
- Cost equal to price pushed into QBO. Rejected if the integration posts cost
  of goods, because real supplier bills and contractor payments already carry
  the cost; cost must then be $0 on the project item.

**Revisit when:** the bank feeds are repaired and the ~$142k October climb in
Undeposited Funds has drained; the accountant has explained the standing ~$47k
September residue; the cost-of-goods posting setting has been checked; or the
accountant asks for the backlog to be dated into a closed HST period as QBO
sales receipts instead.

## Addendum 2026-10-22

Part 3 narrowed: net 0 applies only when the project's cost is unknown or
already buried elsewhere. When the subcontractor invoice is paid and coded in
QBO, the sale is rung at full price to the real customer with a labour line
costed at $0 (if the integration posts cost of goods) or at the invoice amount
(if not). First case: Munsif | Toronto, Luxevista Construction invoice
2026-10-02. Procedure in titan-bookkeeper `docs/financial-flow.md`, 5a.

## Related
- [[QuickBooks]], [[Lightspeed]]
- titan-bookkeeper `docs/financial-flow.md` (procedure and open questions),
  `docs/consolidated-bank-rules.md` (the three Undeposited Funds rules)
