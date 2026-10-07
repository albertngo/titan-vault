---
type: decision
visibility: admin
status: decided
date: 2026-10-07
---

# AEO content engine: design decided, Phase 0 built

**Decision (Albert, grilled in session, 2026-10-07):** build the blog / AEO content engine
as the Marketing department's fourth flow in [[titan-agents-repo]], per
`methods/content-engine-plan.md` there. Twenty-four design questions were put to Albert
with a recommendation each and answered; the grilling skill is now to be run before any
plan ("also, run this skill when you're planning").

**The shape:** a scored Topic Backlog in Notion → one AEO-structured post per topic
(brief → draft → **one human gate**, `Review → Approved` in Notion) → MDX pull request on
`titan-website` (flat slugs; Albert merges) → daily sweep → monthly attribution of won
deals by `utm_campaign` = topic-cluster slug, which feeds the ranking. Two axes on every
post: `Material` (pillar / links) and `Topic Cluster` (scoring / campaign). Video is
repurposed from the blog afterwards, never the reverse.

**Albert's words, where they decide something:** the 106 WordPress posts are in scope;
Next.js only, build `/blog` now; Notion until publish, then MDX is canonical; "I already
have supabase, is that viable? If not then hosted on openseo first, less work right now"
(hosted first; Supabase is the later database, not the host); gap domains "the more the
merrier"; two posts a week; the weekly routine drafts two posts into Review and never
opens a PR; text-only posts first; DataForSEO capped at $1 per harvest and $20 a month.

**What was built in Phase 0 (same day):**
- Notion: **Topic Backlog** database under Blog Content (db `1fb201bb-56d1-449f-9229-f9d0ec117bcf`,
  data source `collection://91bd484f-88b9-47d2-ba13-abcc5efd34a1`); Blog Posts gained
  `ID` (BP), `Topic Cluster`, `Slug`, `Snippet`, `Video URL`, `PR URL`, `Topic`,
  `Content Idea`, `Pillar` / `Spokes`; Titan Content Ideas gained `Topic Cluster`; Titan
  Projects gained `Campaign`.
- Repo: `platform-settings/content-engine.json` (every id, the 8 clusters with priors, v1
  scoring weights, `write_mode: plan_only`), `platform-settings/titan-facts.md` (Albert
  fills), `methods/content-engine.md`, `blog-actions-agent`, nine stub commands,
  Marketing department wiring, actions-log vocabulary, CLAUDE.md section,
  `tests/test_content_engine_registry.py`.

**Still Albert's, before Phase 1 can finish:** rename the Blog Posts `Status` option
`Posted → Published` and add `Briefed`, `Review`, `Approved` in the Notion UI (a status
option cannot be renamed through the API path used); fill `titan-facts.md` with the
prices he is willing to publish; later (Phase 3) make the GHL form write the existing but
empty `UTM_*` contact fields and add `Campaign` to Make 3710214.

**Guards that stay:** the run never writes `Approved`, never merges, never deletes, never
quotes a price outside `titan-facts.md`, never links Speers, never spends past the caps,
never changes a weight or `cluster_performance` on its own.

**Revisit when:** Phase 1's first post is live (the `write_mode` flip is its own dated
note), when the first attribution proposes cluster values, or when DNS cuts over to Vercel
(the sweep's "live" host changes then).
