---
type: decision
visibility: admin
status: decided
date: 2026-09-14
---

# Social plan cover resolution: frame-offset fallback when no cover image exists

**Decision (Albert, in session, 2026-09-14):** for any surface whose
`social-destinations.json` `cover` mode is `image_url` (Facebook Page,
Instagram Reels, YouTube - Shorts, YouTube - Long, TikTok, and LinkedIn if
ever enabled), when `scripts/content_media_select.py` finds no cover image in
Drive's `03_FINAL`, `/content-schedule` now falls back to Metricool's
`videoCoverMilliseconds` field (a millisecond offset into the video, used as
the cover frame) instead of sending no cover at all. The offset comes from
the idea's `Cover Frame (ms)` property on Titan Content Ideas (fetched via
the Calendar Log row's `Content Series` relation), defaulting to `0` when the
idea doesn't set one. A resolved cover image still wins whenever one exists —
`videoThumbnailUrl` and `videoCoverMilliseconds` are alternatives per
Metricool's own `createScheduledPost` contract, never sent together.

**Why:** confirmed against Metricool's own tool contract that
`videoCoverMilliseconds` is a first-class alternative to a cover image, not a
speculative or dependent field — "Alternative to videoThumbnailUrl... Same
requirements and network applicability." The pipeline had the field named in
`cover_rules` since 2026-09-12 but never resolved or sent it; a row with no
cover image simply posted with no custom cover at all.

**Alternatives considered:** holding the row instead of defaulting to 0ms
when the idea sets no offset (consistent with how this pipeline treats every
other unresolvable "which asset" choice — media selection, GBP video-vs-
caption — as unsafe to guess). Albert chose the default over the hold
explicitly. Also considered: a duration-based default (e.g. 10% into the
video) instead of a fixed 0 — rejected for now as needing the video's length,
which nothing in this pipeline currently fetches.

**Consequence worth flagging:** this quietly retires the practical effect of
the `youtube_long_no_cover` hold (a YouTube - Long row with no Drive cover
used to hold rather than let YouTube auto-generate a thumbnail; it now
resolves `frame_offset` at the idea's ms or 0 instead). See
`contracts/social-plan-schema.md`.

**Revisit when:** a frame-offset cover posts visibly wrong (mid-blink, black
frame, motion blur) on a row that never got hand-checked — at that point
either the 0ms default or the no-review path itself should be reconsidered,
not just that row's `Cover Frame (ms)` fixed after the fact.

## Related
<!-- [[2026-09-14-social-write-mode-live]] -->
