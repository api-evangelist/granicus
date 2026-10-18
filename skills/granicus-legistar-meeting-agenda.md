---
generated: '2026-10-18'
method: generated
name: granicus-legistar-meeting-agenda
title: Find meetings and agenda items
description: Find a legislative body's meetings (events) in a date range with OData $filter, then list each meeting's agenda items.
api: openapi/granicus-legistar-openapi.yml
operations:
- Bodies_GetAll
- Events_GetAll
- Events_Get
- EventItems_GetAll
source: openapi/granicus-legistar-openapi.yml; https://webapi.legistar.com/Home/Examples
---

# Find meetings and agenda items

Find a legislative body's meetings (events) in a date range with OData $filter, then list each meeting's agenda items.

## Base and auth
Base URL `https://webapi.legistar.com/v1/{Client}`, where `{Client}` is the jurisdiction's Legistar client name. Most clients allow anonymous read-only access; when a call returns unauthorized, that client needs an API token passed as `?token=...` (see the client's token policy).

## Steps
1. `Bodies_GetAll` — list the client's legislative bodies to find the BodyId you care about.
2. `Events_GetAll` — list meetings; narrow with `$filter=EventDate ge datetime'YYYY-MM-DD' and EventBodyId eq <BodyId>`.
3. `Events_Get` — fetch one meeting by EventId.
4. `EventItems_GetAll` — list agenda items for that EventId.

## Rules
- Replies are capped at 1000 results; page with `$top`/`$skip`.
- Filters follow OData v3 URL conventions.
- These skills use read-only GET operations; the spec's POST/PUT/DELETE operations change the client's legislative record and are idempotent only for PUT/DELETE by id.
