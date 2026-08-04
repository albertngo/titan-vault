---
type: platform
visibility: admin
status: active
last_activity: 2026-08-02
---

# Outlook (Microsoft 365)

Titan's email surface: customer quote requests and scheduling, supplier price
lists and order confirmations, and everything administrative that never touches
[[GHL]] or [[Notion]] — accountant, bank, insurance, legal, telecom, landlord,
collections. Read by `outlook-ingest-agent`; nothing writes here.

**Admin-only surface.** Staff have no window onto these mailboxes, so every fact
derived from Outlook is admin-level regardless of subject — see CONVENTIONS
Visibility rule 4. The ingest source default for `outlook` is `private`
(`platform-settings/notion-destinations.json`), i.e. `admin` in vault terms.

**Access:** app-only Microsoft Graph, via `scripts/outlook_pull.py` in
titan-agents. **Not** a claude.ai connector. A session connector cannot survive a
scheduled run and is unreachable from a subagent when the session defers tools —
proven twice on 2026-08-02 before the app-only path was built. Anything that
needs to run unattended must go through the script.

| Setting | Value |
|---|---|
| Azure app | `titan-agents-ingest` |
| Client id | `a8f145e0-01e1-40e8-a3a6-613d75b00697` |
| Tenant id | `dcac9487-44d0-4a3e-96b2-413bef60bbf4` |
| Client secret | **never recorded in this vault** — env only; see `.env.example` in titan-agents |
| Permission | `Mail.Read` (application), admin-consented |

**Secret expiry: 24 months from 2026-08-02.** An expired secret fails exactly
like a platform outage — `status: "error"` ingest files, no loud signal. If
Outlook "goes down" near mid-2028, check the secret before debugging Graph.

## Mailboxes ingested

| Mailbox | Notes |
|---|---|
| `albert@` | Admin/finance/legal threads; most of the volume |
| `info@` | Public inbox: inbound quote requests, supplier lists, e-Transfer forwards |
| `pourya@` | Sales — customer scheduling, partner quotes |
| `mike@` | Very low volume |

`info@` has **no delegate access for Albert personally**, but app-only reads it
fine — the two are different access models entirely. Assuming delegate access
implies app access (or vice versa) cost a full debugging cycle.

## Scoping — RESOLVED 2026-08-03 (was an open risk 2026-08-02)

Access is narrowed by an Exchange **Application Access Policy**
(`AccessRight: RestrictAccess`, `IsValid: True`) scoped to the mail-enabled
security group **`titan-ingest-mailboxes@flooruca.onmicrosoft.com`** —
GUID `784742b3-2735-4a8c-8a35-1b446dab7d5f`. All four ingest mailboxes verified
readable after it applied.

**The group is on the `onmicrosoft.com` domain, not `titanfloors.ca`.** It was
created without an explicit `-PrimarySmtpAddress`, so Exchange assigned the
tenant's default domain. Every command that referenced
`titan-ingest-mailboxes@titanfloors.ca` failed with "couldn't be found" until
this was spotted. The address is irrelevant to function — the group is a scoping
object, never emailed — but use the `onmicrosoft.com` address or the GUID.

Prior state, for the record: on 2026-08-02 the group did not exist and the app
held **tenant-wide `Mail.Read`**, confirmed by reading 72 messages from a mailbox
that should have been out of scope. Between app creation and policy application,
an app-only registration reads *every* mailbox in the tenant — treat that window
as the real exposure, and close it in the same sitting.

Still unproven: that an out-of-scope mailbox now returns 403. Titan may have no
mailbox outside the four to test against, in which case the policy's value is
forward-looking — any mailbox added later is denied by default.

**Setup traps worth keeping** (each cost a round trip):

- `Connect-ExchangeOnline` is **per-session**. A new `pwsh` window has no
  Exchange cmdlets at all — `New-DistributionGroup` reports "not recognized as
  the name of a cmdlet", which reads like a missing module, not a missing login.
- `New-ApplicationAccessPolicy` on a tenant with **no** policies makes
  `Get-ApplicationAccessPolicy` fail with an `OU=... couldn't be found` error.
  That is the empty state, not a fault.
- "There are multiple recipients matching identity" on group creation means the
  group already exists from an earlier attempt. Enumerate with `Get-Recipient`
  and reuse it; identify by GUID to avoid the ambiguity entirely.

## Quirks and traps (each cost real debugging time — do not re-derive)

- **Graph folder names are not the display names.** Use `SentItems`,
  `JunkEmail`, `DeletedItems` — not "Sent Items", "Junk Email", "Deleted Items".
- **`receivedDateTime` is UTC.** Convert to America/Toronto before comparing to
  a window or writing a date anywhere; an unconverted timestamp silently shifts
  items across day boundaries.
- **A 403 on one mailbox means it is missing from the access-policy group** —
  it is not an outage and not a token problem. Fix the group membership.
- **Exchange Online PowerShell cmdlets only exist after `Connect-ExchangeOnline`**,
  and that connection is per-session. A "cmdlet not recognized" error usually
  means the connect step was skipped, not that the module is missing.
- **Interac e-Transfer receipts arrive as `FW:` from `info@` with importance
  high.** They are *incoming money* — never treat them as something due. The
  high-importance flag is the forwarder's, not a signal of urgency.
- **Reply detection is Sent-Items-based**, so "no reply found" means no *written*
  reply in the window — a phone call or in-person visit leaves no trace.

## Log

- 2026-08-02 — First successful Outlook ingest ever, after five consecutive
  failed run-days (07-26 → 08-01) under the connector approach. App-only Graph
  path built and proven: 135 messages scanned across 4 mailboxes, 35 items kept,
  69 noise-skipped. Ran as a 7-day catch-up (168h window, capped at
  `max_catchup_days=7`, covering 2026-07-26 18:00 → 2026-08-02 18:00
  America/Toronto) because the source had been dark for a week; anything before
  2026-07-26 is still unscanned. Day recorded in [[2026-08-02]]. Tenant-wide
  `Mail.Read` scoping risk opened the same day, closed 2026-08-03.
