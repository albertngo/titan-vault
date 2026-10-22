---
type: decision
visibility: admin
date: 2026-10-22
status: decided
---

# The quote email is branded in the logo's blue, sent from the person signed in, and every version keeps an edit history

**Decision:** Three parts, all Albert, 2026-10-22, built the same day in titan-desk
`quote/` (branch `claude/keen-wozniak-57ncfb`, commit 2300fe7).

1. **The quote email recreates the GHL "Rough quote is ready" template and improves
   on it.** Kept: the cream header band with the logo, the dark ink, the shape a
   customer already knows (greeting, what's included, the total, one button, next
   steps, footer), and the in-store visit as a preliminary's next step. Changed: warm
   paper instead of the pale blue page, the logo at letterhead size instead of column
   width, a serif headline in a plain sentence instead of the emoji "Hey Name", small
   eyebrows instead of underlined titles, a left-aligned card per option with the
   total set large, a pill button, the payment schedule in words, and a transactional
   footer. The photo carousel, click tracking and unsubscribe line are gone: a quote
   is transactional. **The accent is the logo's own blue (`#283890`), not the
   template's terracotta** (Albert: "you use your skills to decide which colorway").
   The customer page and PDF still use RiderBlue (`#1e6fff`) and should follow.
2. **The email goes out from the email signed into the app**, not from the location's
   default. Until today every quote the app sent went out as "Titan Flooring Inc.
   <albert@titanfloors.ca>" under Albert's GHL user, whoever was logged in. The send
   now passes GHL's `emailFrom` as the quoter's own address, tried as "Albert @ Titan
   Flooring <albert@…>", then the bare address, then GHL's default, so a refused
   sender costs a retry and never the send. Only an address on the letterhead's
   domain is offered: GHL sends only from a domain it has verified. The person comes
   from the Microsoft sign-in; the first name signs the email and the text, and a
   shared box (info@) signs as the company.
3. **Editing and saving keep a history of the person working on the file.** Quote
   Versions gained four fields in Airtable: `Created By (app)`, `Last Edited By`,
   `Last Edited At`, and an append-only `Edit Log` (Toronto time, the signed-in
   email, what changed). The app writes them in the same update as every save, new
   version, quick-form fill and send. The quote page shows a History card, staff only.

**Why:** The old template was a marketing email pressed into transactional duty, and
two of its three live copies still printed the old Matheson Blvd address. The sender
mattered because replies and credit should land with the person who quoted, and
because a customer who met Pourya should hear from Pourya. Airtable's own
last-modified fields would name the app's single token for every write, so the app
has to record the person itself. Make scenario 4975508 forwards the message body
verbatim, which is why none of this needed a change in Make.

**Alternatives considered:**
- A GHL builder template by id (`templateId`). Rejected: the per-quote content would
  have to travel through contact custom values the app deliberately never writes,
  and the tests that pin what a customer can and cannot see would no longer cover it.
- Sending from the quoter's own Outlook mailbox through Microsoft Graph, relying on
  GHL's Outlook sync to pull it into the conversation. Held as the fallback if GHL
  refuses `emailFrom` on the company domain; it is a new write path with a new scope.
- Terracotta accent to match the old template. Rejected: the logo is royal blue, and
  the customer sees the email, the link and the PDF together.
- A separate edits table. Rejected for now: a fourth-table write is a boundary
  change; one append-only text field on the version is enough until someone needs
  to query it.

**Still to do:** set `QUOTE_LOGO_URL` on both quote deployments and `QUOTE_BOOKING_URL`
on the staff one; make the first real send to a test contact and read the From
header, which is the only true test of the named From line; align the customer page
and PDF accent with the email.

**Revisit when:** GHL rejects the company-domain `emailFrom` (then the Graph route),
or a second app needs the edit history as rows rather than text.

## Log
- 2026-10-22 — Decided and built. Albert's words: "we do want the quote to be sent out
  from the email logged into the app. editing and saving should also have a history
  of the person working on the file at that time."
