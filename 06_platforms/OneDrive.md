---
type: platform
visibility: admin
status: active
last_activity: 2026-09-01
---

# OneDrive

Titan's file layer, on the `info@titanfloors.ca` OneDrive for Business drive
(`flooruca-my.sharepoint.com`). Holds `TITAN FILES/`, `MEDIA FILES/`, and
`Price List (Attachments)/` — the last being the automated landing folder for
every supplier price list Titan receives, and the reason this note exists.

Supplier PDFs arrive here by automation, not by hand: a Make scenario watches
[[Outlook]] twice daily, downloads each attachment, uploads it to
`Price List (Attachments)/`, creates an anonymous share link, and writes a row to
the [[Notion]] "Price Lists" database carrying that link. **Notion is therefore the
index of every price list ever received** — tagged by company and Promo/Regular —
and the share link on the row is the way to get the file itself.

**Access:** claude.ai Microsoft 365 connector (Anthropic-managed, OAuth). It is a
read/write connector for search, folder and upload operations — but see the traps
below for what it cannot do. `sharepoint.com` is reachable from cloud sessions;
no network-policy change is needed.

## Quirks and traps (each cost real debugging time — do not re-derive)

- **The connector never returns file bytes.** `read_resource` on a PDF or Office
  document returns Microsoft Graph's *text conversion*, not the file. Anything
  needing real bytes (pdfplumber, geometry, table structure) cannot use it. Graph's
  conversion also flattens table layout — stock markers land mid-row rather than on
  their own line — so it silently degrades extraction accuracy too.
- **Share links need `?download=1` AND a cookie jar.** The links on the Notion rows
  are anonymous-scoped but tenant-served. Without `?download=1` SharePoint returns
  ~275KB of viewer HTML that saves happily as a `.pdf`; with `curl -L` but no
  cookie jar the redirect chain drops the `FedAuth` cookie and returns **403**
  (`x-msdavext_error: Access denied`). Verified working recipe and a wrapper live
  in titan-agents: `scripts/pricelist_fetch.py`, method note
  `methods/pricelist-extraction.md`.
- **The drive-root listing silently omits folders that exist.** Reading the drive
  root returns only 3 items and does not include `Price List (Attachments)` —
  yet attempting to create a folder of that name at root returns CONFLICT, proving
  it is there. Absence from a listing is not evidence of absence.
- **`sharepoint_folder_search` ignores its `name` filter.** Queries for
  "Price List (Attachments)", "Price List" and "Attachments" all returned the same
  unrelated images and videos. Treat the tool as non-functional.
- **`sharepoint_search` with `folderName:` does work** and is the fast, reliable way
  to find a file or confirm a path inside a known folder.
- **`read_resource` resolves multi-segment file paths but not bare folder paths.**
  `file:///{driveId}/Price List (Attachments)/Green Touch Price list 2026 Sept.1.pdf`
  works; the same path stopping at the folder returns `invalidRequest` — the
  connector treats a single trailing segment as an itemId, not a path.
- **Uploading into an existing folder is currently blocked.**
  `sharepoint_create_folder` / `sharepoint_upload_file` require the parent's Graph
  `parentItemId`, and no available tool surfaces it for a folder (root listing omits
  it, folder search is broken, the CONFLICT error exposes only hashes). Getting the
  id from the OneDrive UI once and recording it here would close this permanently.

## Log

- 2026-09-01 — Note created on Albert's explicit instruction, from the GreenTouch
  2026-09-01 price-list run ([[Greentouch]]). Share-link → cookie-jar → pdfplumber
  chain verified end to end (786KB, 10-page PDF; 82 of 83 SKUs cross-checked
  against the pushed Airtable costs with zero mismatches). Upload-side blocker
  (parent folder itemId) recorded but unresolved.
