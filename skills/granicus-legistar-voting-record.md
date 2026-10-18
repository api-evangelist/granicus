---
generated: '2026-10-18'
method: generated
name: granicus-legistar-voting-record
title: Get a voting record
description: Get roll calls and votes on agenda items, or a single person's full voting record.
api: openapi/granicus-legistar-openapi.yml
operations:
- Persons_GetAll
- Votes_GetByNameId
- EventItems_GetAll
- Votes_GetAll
- RollCalls_GetAll
- VoteTypes_GetAll
source: openapi/granicus-legistar-openapi.yml; https://webapi.legistar.com/Home/Examples
---

# Get a voting record

Get roll calls and votes on agenda items, or a single person's full voting record.

## Base and auth
Base URL `https://webapi.legistar.com/v1/{Client}`, where `{Client}` is the jurisdiction's Legistar client name. Most clients allow anonymous read-only access; when a call returns unauthorized, that client needs an API token passed as `?token=...` (see the client's token policy).

## Steps
1. `Persons_GetAll` — find the PersonId of the official.
2. `Votes_GetByNameId` — every vote cast by that person.
3. Or per meeting: `EventItems_GetAll` for the EventId, then `Votes_GetAll` and `RollCalls_GetAll` for each EventItemId.
4. `VoteTypes_GetAll` — decode vote values.

## Rules
- Replies are capped at 1000 results; page with `$top`/`$skip`.
- Filters follow OData v3 URL conventions.
- These skills use read-only GET operations; the spec's POST/PUT/DELETE operations change the client's legislative record and are idempotent only for PUT/DELETE by id.
