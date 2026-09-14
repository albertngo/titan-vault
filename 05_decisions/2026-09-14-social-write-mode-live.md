---
type: decision
visibility: admin
status: decided
date: 2026-09-14
---

# Social pipeline write_mode flipped draft → live

**Decision (Albert, in session, 2026-09-14):** `platform-settings/social-destinations.json`
→ `write_mode.mode` changed from `"draft"` to `"live"` in
[[titan-agents-repo]]. Every post the content-schedule/social-actions pipeline
schedules from now on carries `info.draft: false` — it will actually publish
at its scheduled time, not sit as a Metricool draft. This was the staged
rollout gate Albert set 2026-09-12 ("every write goes out as a Metricool
draft until this flips... a dated decision, not a quiet edit"); this note is
that dated decision.

**Why:** Albert asked directly why the TC-86 Instagram Reel scheduled earlier
today ("Staircase Transformation") was only landing as a draft, and said he
wanted it actually scheduled. The two-brake design (draft flag + approval
file) had done its job — the pipeline ran end-to-end successfully for the
first time today (see actions-log 2026-09-14, action `17a4860e`) — and Albert
judged that enough to lift the first brake.

**Scope:** this is a global, repo-wide switch, not a one-post override. It
affects every future `social_schedule_post` / `social_reschedule_post` /
`social_update_post` action, on every surface, from every source
(`/content-schedule`, `/content-sweep`'s drift-reschedule proposals). The
approval-file gate is unchanged and still applies to every write.

**Alternatives considered:** leaving write_mode on draft and only converting
the one already-scheduled TC-86 post to live by hand. Rejected — Albert's
instruction ("make the writes live and not go to draft") was general, not
scoped to the one post, and a per-post override with no registry change would
leave the next scheduled row landing as a draft again, silently.

**Revisit when:** a bad live post ships (wrong caption, wrong asset, wrong
timing) that the two-brake design was built to catch before a customer saw
it — at that point the tradeoff this note records should be re-examined, not
just the offending row fixed.

## Related
<!-- [[2026-09-14-social-cover-frame-fallback]] -->
