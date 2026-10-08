---
type: decision
visibility: admin
status: decided
date: 2026-10-08
---

# GHL unread triage: one rubric, an hourly sweep, one "waiting on us" list

**Decision (Albert, grilled in session, 2026-10-07/08):** make the [[GHL]] unread count mean
*needs a human response*, per his spec (GHL_Unread_Triage_Spec.docx), built in
[[titan-agents-repo]] (`methods/ghl-unread-triage.md`, `/ghl-triage`).

- **One rubric, two callers.** `methods/ghl-unread-triage.md` is the only copy of the
  classifier. The session model reads it in both the hourly sweep and the daily brief.
  Verdicts: `NEEDS_RESPONSE`, `CLOSER`, `SPAM` (added in grilling), `UNSURE`.
- **What a batch is.** Everything the customer sent since Titan's last **human** reply. An
  automation never ends a batch, so a reminder can't bury an open question under a
  "thanks". Photos, empty bodies, calls, voicemails and unknown message types are held
  before the model sees them and always stay unread.
- **Guards, only ever toward a human.** A `?` or a message over 200 characters vetoes
  `CLOSER`. `SPAM` stands only for a stranger: never a human reply from Titan, no
  opportunity, no other conversation. Suppliers and trade services are never spam.
- **Rulings on the first live dry run** (2026-10-08: 377 unread, 177 judged):
  - a plan to follow up ("still deciding, will let you know") → `CLOSER`;
  - a cancel request and a bare time → `NEEDS_RESPONSE`;
  - a vague fragment → `UNSURE`;
  - bin-rental and estimating pitches → `UNSURE`;
  - website and lead-generation pitches → `SPAM`.
  Rulings only, not a list of reworded real messages (rubric v2).
- **The sweep** is a Claude Code routine, hourly 8am–9pm Toronto, Mon–Sat, in the
  price-list environment. Its only write is `scripts/ghl_mark_read.py`: one request, `unread
  count = 0`, its own `conversations.write` token, run by `ghl-actions-agent` on a policy
  approval file.
- **Pilot first.** It runs `plan_only`: it logs "would clear" and marks nothing read.
  `CLOSER` and `SPAM` each have their own switch:
  - closers: at least 7 days and 50 verdicts, none wrong;
  - spam: at least 7 days and 20 verdicts, none wrong.
  A wrong one fixes the rubric and restarts that clock. Switching on is its own dated
  decision. It also needs the token, a supervised write probe, and a dated CLAUDE.md
  exception for `ghl-actions-agent`.
- **Cap.** At most 25 marked read per run, all-or-nothing: over the cap, nothing is marked
  and a push goes out. The pilot's backlog is cleared once, supervised, at the switch.
- **The log** goes to branch `claude/ghl-triage-log`, never merged and never PR'd. It is
  also the verdict cache. It holds ids, verdicts and paraphrased reasons. Customer
  excerpts get turned on only once the repo is private: Albert's call, "later, not a
  blocker".
- **The brief** becomes one "waiting on us" list: the 24 h window plus everything unread.
  - Closers and spam drop out from pilot day one; the brief ends with a full "would clear"
    list.
  - Anything waiting 24 h or more is flagged.
  - Customers quiet for 14+ days (by their latest message) become one count line.
  - notion-sync is unchanged.
  - `unanswered_conversations` changes meaning; accepted.
- **The brief never marks anything read.** The sweep is the only writer. Failures show in
  the brief; writer errors also push a notification.

**Why:** GHL keeps a conversation unread until someone replies, so the count is padded with
"sounds good, see you Tuesday" and the real pile is invisible. Wrongly silencing a real
question is the worst outcome, so every rule leans toward a person seeing it.

**Alternatives considered:**
- GitHub Actions + a Python script calling the Claude API (no new runtime needed, but
  adds a separate API key and spend); Make (the prompt would live in two places).
- A PR per fire instead of a log branch: about 14 a day.
- Clearing old backlog conversations, or answered-but-still-unread ones: out of scope
  for now, closers and stranger spam only.
- Rolling 20-per-run instead of all-or-nothing.

**Revisit when:** each switch flips (its own decision note), the repo goes private
(excerpts on), or the pilot shows a pattern the rulings get wrong.

## Related
[[GHL]] · [[titan-agents-repo]] · [[2026-10-02-call-notes-internal-comment]]
