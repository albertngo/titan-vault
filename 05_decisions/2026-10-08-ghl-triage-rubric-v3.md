---
type: decision
visibility: admin
status: decided
date: 2026-10-08
---

# GHL unread triage rubric v3: reply, act, know, clear

**Decision (Albert, reviewing the 2026-10-08 dry run):** [[GHL]] unread triage gets two more
verdicts, so a message that needs a person but no text reply is neither counted as "waiting
on a reply" nor marked read unseen. Rubric v3 in [[titan-agents-repo]]
(`methods/ghl-unread-triage.md`); where it differs, it supersedes the rulings in
[[2026-10-08-ghl-unread-triage]].

| Bucket | Verdict | Marked read? | Brief |
|---|---|---|---|
| reply | `NEEDS_RESPONSE`, `UNSURE` | never | waiting on a reply: 24 h flag, Notion task (unchanged) |
| act | `ACTION` (new) | never | "to action": Notion task |
| know | `FYI` (new) | never | "FYI": no task, no age flag, listed once |
| clear | `CLOSER`, `SPAM` | only once its switch is on | "would clear" / "cleared" |

- **ACTION** covers:
  - an address, unit or buzzer code, email, phone or location;
  - an arrival, pickup or visit notice, or a payment notice;
  - site logistics for the crew, or a cancel request.

  Missed calls and attachments are still held before the model sees them, and now show
  under "to action": call back, check the attachment.
- **An opt-out is ACTION with a `compliance:` reason**, because someone has to set DND. It
  outranks everything else in its batch. It is never cleared and never dropped into the
  backlog count.
- **FYI** covers:
  - a lost or declined job;
  - "still deciding, I'll let you know" (it was `CLOSER`);
  - praise, reviews and referrals;
  - third parties, job seekers, and supplier or trade pitches, which are never `SPAM`.

  The brief lists an FYI once, the day it arrives.
- **CLOSER narrows to pure acknowledgement:** thanks, 👍, "sounds good", and reactions to our
  messages.
- **A bare time or a bare yes/ok/sure stays on the reply list.** The review settled this:
  every such row was accepted as a reply.
- **Mixed batches:** an opt-out wins, then any open question (reply), then act, then know,
  then clear.
- **The review of run `20261008T1252-e2a9`** (375 unread) overrode no proposed bucket.
  Judged against v3, 17 of 49 `CLOSER` verdicts were wrong: 15 "still deciding" and 2
  praise or referral, all now `FYI`. None was wrong under v2's own rules. `SPAM` was right 3
  of 3 times. `CLOSER`'s pilot clock restarts with v3; `SPAM`'s does not.
- **Unchanged:** `plan_only`, no verdict switched on, the cap, the CLOSER veto and the
  stranger-only SPAM guard. The version bump discards every cached verdict.

**Why:** under v2 these messages were either `NEEDS_RESPONSE`, which inflated the reply list,
or `CLOSER`, which would have them marked read unseen. Examples are an address, a note that
the customer is on the way to pay, and a missed call. Neither outcome is right.

**Alternatives considered:**
- An `ACTION` "confirm" for bare times and yes/ok/sure. The review kept them as replies.
- `NEEDS_RESPONSE` with a sub-label. That keeps the reply list inflated.
- Clearing FYI. FYI is never marked read; it is listed once and counted after that.

**Revisit when:** `CLOSER` meets its pilot bar under v3, the to-action or FYI lists get too
long to read, or the pilot shows a pattern v3 gets wrong.

## Related
[[GHL]] · [[titan-agents-repo]] · [[2026-10-08-ghl-unread-triage]]
