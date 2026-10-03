---
type: decision
visibility: admin
status: decided
date: 2026-10-02
---

# Calls land in GHL: transcript in Notes, summary as an internal comment

**Decision (Albert, in session, 2026-10-02):** every completed call or voicemail of
8 s or more is transcribed and written back into GHL by Make scenario "GHL Call -> Note"
(4951497) in [[titan-agents-repo]], fired by the GHL "Call Status" workflow (webhook is
its only action). The full transcript goes in the contact's **Notes**; Summary + Next
steps go in an **internal comment** on the conversation, beside the recording. Both carry
the call line (date and time, direction, duration, staff) and the same `Ref C-MMDD-HHmm`.
Live since 14:17 UTC.

Albert's words: "After the call, an internal note instead for the summary and next
steps. Then a reference code in the internal note -> referencing to the transcript in
notes", then "make it explicit to internal comments only. Make a barrier to do so with
no slip ups."

**The barrier:** the comment has its own one-scope GHL key, used by one module; the
request's `type` is a literal last key and the text is JSON-escaped by Make; an
exact-body pattern filter must pass before the post; GHL's read-back of the message type
must say internal comment, or a WhatsApp alarm goes to Albert and a kill switch blocks
every later comment until he clears it (alarm confirmed received on his phone). The
daily GHL run also alarms if a summary ever shows up as anything else. A test pins every
layer against a snapshot of the scenario.

**Engine and model:** ElevenLabs Scribe v2 transcribes (GHL's own transcript was the
quality being replaced; Deepgram dropped). Claude writes the summary: Haiku 4.5 under
5 minutes, Sonnet 4.5 from 5 minutes ("make it switch depend on length"). The language
is detected; a non-English call (Mandarin, Cantonese, Vietnamese, Farsi, …) still gets
an English summary, plus a full English translation as its own note series.

**Who is named (tightened the same evening):** a call on a person's own GHL line
(Albert, Pourya, Mike) names that person, decided by Make, not the model. The Front Desk
line is "Staff" unless the Titan person introduces themselves ("this is Joey"); a
customer using a name, or a colleague called out across the room, does not count. The
first live call had named Pourya because Joey called out "Pourya?" mid-call; that is
what forced the rule. Every transcript line is labelled `Customer`, `Staff`,
`Staff (Joey)` or `Other` ("make it perfectly clear speaker 1 and speaker 2 is"), and a
label only carries a name the call-level rule allowed.

**Alternatives considered:** Summary + Next steps at the top of the transcript note (v1,
replaced the same day: notes bury it, the comment sits beside the recording); Sonnet for
every call (Haiku is about half the cost on short calls and good enough there); naming
from the model's reading of the call (it guessed wrong on the first live call).

**Cost:** about 25–42 Make credits a call (operations plus the Claude step), most of it
the summary.

**Revisit when:** the WhatsApp alarm ever fires; a call on a personal line shows the wrong
label; the first real Cantonese call (not yet confirmed in ElevenLabs' language list);
staff start answering "Titan Flooring, this is …" consistently (names would then appear
on most Front Desk calls).

## Related
[[GHL]] · method: `methods/ghl-call-transcripts.md` · registry:
`platform-settings/ghl-calls.json`
