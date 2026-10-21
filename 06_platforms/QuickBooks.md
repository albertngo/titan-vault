---
type: platform
visibility: admin
status: active
last_activity: 2026-10-21
---

# QuickBooks Online (QBO)

Titan's books: revenue, HST, expenses, bank. **Not** the sale of record and
**not** where A/R is tracked; both are [[Lightspeed]]. QBO receives every sale
from Lightspeed automatically on register closure. Read by nothing in
titan-agents today: `bookkeeper-ingest-agent` has written `status: "error"` on
every run since 2026-07-26 because no QuickBooks connector is configured.

**Admin-only surface.** Everything derived from QBO is admin-level (CONVENTIONS
Visibility; ingest source default `private`).

**Canonical detail lives in titan-bookkeeper, `docs/financial-flow.md`.** This
note holds what an agent or a future session needs to not break the books. Add
quirks here; add procedure there.

## How money reaches the books (confirmed 2026-10-21)

1. A sale is rung in [[Lightspeed]]. Nothing posts until the register is closed.
2. On closure Lightspeed posts to QBO an **Invoice plus Payments by tender
   type**, payee `Mississauga Outlet | Right Register`, account A/R, deposited to
   **Undeposited Funds**. Sales rung with a customer attached post under that
   customer's name instead. Posting date is the closure date.
3. The bank feed later shows the deposit. It is posted **against Undeposited
   Funds** (Match, Categorize to Undeposited Funds, or Transfer: identical
   entries), never to Sales. A sale deposit categorized to income is a
   double-counted sale.

**Undeposited Funds is the clearing account.** Its balance should equal cash in
the safe plus card batches in transit, and nothing else. Reconciled by whole
balance per month, not line by line (decision
[[2026-10-21-undeposited-funds-whole-balance]]).

## Quirks and traps

- **New Banking page rejects Transfer to Undeposited Funds** ("An unexpected
  error occurred while accepting your downloaded transaction", 2026-10-21). Use
  Categorize, or the previous version of the page. The three money-in bank
  rules must be type Categorize.
- **Customer e-transfers all read `INTERAC ETRNSFR AD RECVD ALBERT NGO`** because
  they are forwarded through Albert's account. The customer is known only from
  [[Notion]]'s Master Payments Log. Worklist is Notion, not the feed.
- **Card settlements arrive net of fees** (BMO memo "Not Service Chargeable");
  Lightspeed posts gross. Fees must be moved out of Undeposited Funds, by split
  or by a monthly journal entry, or they accumulate there forever.
- **Bank feeds broken** (accountant, 2026-10-20): BMO and TD, 4 accounts. A
  reconnect may re-import transactions; exclude duplicates, never categorize.
- **Rule importer rejects `/` or `:` in a rule name** and caps a rule at about
  6 conditions (titan-bookkeeper `docs/consolidated-bank-rules.md`).
- QBO Match offers are hints. A wrong Match changes no balance under whole
  balance; it only consumes the wrong "available to deposit" line.

## State observed 2026-10-21

Undeposited Funds **$189,428.94** across 6,019 lines. Held at about $47k to
$56k through September with daily settlement transfers, then climbed about
$142k in October after the feeds broke. The standing ~$47k is the residue to
unwind with the accountant. Open questions (cost-of-goods posting, the
September residue, HST period for the e-transfer backlog, deposits on open
jobs) are tracked in the titan-bookkeeper doc, section 7.

## Make scenarios touching QBO

Folder "Finance & Bookkeeping": 4824368 Register Closure Watchdog (queries QBO
invoices; WhatsApp plus Notion to-do if none in 3 days), 4822446 Sync Chart of
Accounts, 4824058 Create New CoA Accounts (one-time), 4822687 Pull P&L Report,
4841468 Outlook INVOICE -> QBO Receipts. All on-demand.

## Log
- 2026-10-21 — Note created on Albert's instruction after a live register
  closure and Undeposited Funds review. Previously proposed and withheld on
  2026-08-11, 08-23, 08-24, 08-27, 08-30, 09-04, 09-08 (platform notes are
  explicit-instruction only). #admin
