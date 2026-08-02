---
type: platform
visibility: admin
status: active
last_activity: 2026-07-28
---

# Notion

Titan's operational back office: won projects, QA work orders, payments log,
tactical tasks, weekly status meetings. Everything post-win lives here (pre-win
is [[GHL]]). Read daily by `notion-ingest-agent`; written by the `notion-sync`
command (Tactical Tasks List only) and by the team by hand.

**Access:** claude.ai Notion connector (Albert's account) — works for manual and
interactive runs. Not yet wired portably in `.mcp.json`; unattended/scheduled
runs need a Notion internal integration token first, and internal integrations
only see databases explicitly shared with them.

## Databases (verified live 2026-07-28)

| Database | Data source | Read by | Written by |
|---|---|---|---|
| Titan Projects | `collection://1b4596a4-505f-81ca-b1d5-000bb73ecbe1` | ingest | team (via GHL Submit automation) |
| QA Work Orders | `collection://2eb596a4-505f-800a-af8f-000b24ce4c57` | ingest | team |
| Master Payments Log | `collection://26d596a4-505f-8073-a0ac-000b2a8d3a0e` | ingest | team |
| Tactical Tasks List | `collection://238596a4-505f-8137-af13-000bde205213` | ingest | `notion-sync` + team |
| Project Status Meetings | `collection://24d596a4-505f-803a-9797-000b3f8f5a68` | ingest | meeting-processor skill + team |
| (CII) Continuous Improvement | `collection://365596a4-505f-81b2-8eb7-000b068f506c` | (v2) | team |

Machine-readable copies: `platform-settings/notion-ingest-sources.json` (read
side) and `platform-settings/notion-destinations.json` (write side) in
titan-agents — keep them in sync when anything is renamed in Notion.

## Quirks and traps (each cost real debugging time — do not re-derive)

- **Titan Projects has no status field; every row is already a won project.**
  `Date Won` is a `created_time` property — row creation IS the win event,
  triggered downstream of GHL's `2. *Project Won* ` stage. "New project" is
  detected by row diffing, never by filtering a status.
- **`created_time` properties are plain SQL columns; date properties are not.**
  A real date property appears only as virtual columns
  (`date:<Name>:start/:end/:is_datetime`) — but `Date Won` must be queried as
  plain `"Date Won"`; the virtual-column form returns a 400.
- **SQL mode caps at 100 rows with `has_more: true` and NO cursor** (pagination
  is view-mode only). Always `ORDER BY` the date column descending; any
  full-table snapshot must be built as a union across runs, never one pull.
- **Parallel SQL queries trip a 429** (`collection_router_upstream_429`,
  observed with 6 concurrent). Run sequentially; retry once after the
  suggested `retry_after`.
- **Tactical Tasks List has two different "url"s**: every row's own Notion page
  url (universal identity key) vs. the `url` *property* (set only on rows
  `notion-sync` created; null on manual rows). Confusing them breaks dedupe.
- **Project Status Meetings titles are not reliably date-suffixed** (older rows
  are plain "Project Status"). Identify meetings by page url only.
- **Meeting pages hold their content in inline child databases** (action items,
  status updates, playbook) that fetch as empty placeholder tags — each needs
  its own discovery + query. Pages are also bloated by embedded screenshot
  URLs; a full-page fetch can exceed response limits. The cheap read path is
  the `Meeting Summary` property → the meeting-processor skill's output page.
- **`notion-fetch` on a database page returns the entire page hierarchy** and
  can blow the response limit. Fetch `collection://` ids for schema; use SQL
  mode for rows.

## Log

- 2026-07-28 — `notion-ingest-agent` added to titan-agents (PR #3); first solo
  run clean: 44 items, 3 new won projects, 106-day-old deficiency surfaced.
