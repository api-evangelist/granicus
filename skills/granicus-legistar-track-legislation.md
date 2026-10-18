---
generated: '2026-10-18'
method: generated
name: granicus-legistar-track-legislation
title: Track a piece of legislation
description: Search matters (bills, ordinances, resolutions), then pull their history, sponsors, text versions and attachments.
api: openapi/granicus-legistar-openapi.yml
operations:
- Matters_GetAll
- Matters_Get
- MatterHistories_GetAll
- MatterSponsors_GetAll
- MatterTexts_GetVersions
- MatterAttachments_GetAll
- MatterAttachments_GetFile
source: openapi/granicus-legistar-openapi.yml; https://webapi.legistar.com/Home/Examples
---

# Track a piece of legislation

Search matters (bills, ordinances, resolutions), then pull their history, sponsors, text versions and attachments.

## Base and auth
Base URL `https://webapi.legistar.com/v1/{Client}`, where `{Client}` is the jurisdiction's Legistar client name. Most clients allow anonymous read-only access; when a call returns unauthorized, that client needs an API token passed as `?token=...` (see the client's token policy).

## Steps
1. `Matters_GetAll` — find matters; page with `$top`/`$skip`, filter with `$filter`.
2. `Matters_Get` — fetch the matter by MatterId.
3. `MatterHistories_GetAll` — legislative actions taken on it.
4. `MatterSponsors_GetAll` — who sponsored it.
5. `MatterTexts_GetVersions` — available text versions.
6. `MatterAttachments_GetAll` then `MatterAttachments_GetFile` — list and download attached documents.

## Rules
- Replies are capped at 1000 results; page with `$top`/`$skip`.
- Filters follow OData v3 URL conventions.
- These skills use read-only GET operations; the spec's POST/PUT/DELETE operations change the client's legislative record and are idempotent only for PUT/DELETE by id.
