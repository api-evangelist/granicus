---
name: granicus-manage-event-item-votes
description: Create, retrieve, update, and delete votes for a specific event item.
api: openapi/granicus-legistar-openapi.yml
operations:
- Votes_Post
- Votes_GetAll
- Votes_Get
- Votes_Put
- Votes_Delete
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/granicus-legistar-openapi.yml ; every operationId checked against the contract
---

# granicus-manage-event-item-votes

Create, retrieve, update, and delete votes for a specific event item.

## Steps

1. 1. Create a new vote for an event item using `Votes_Post` with the `Client` and `EventItemId` path parameters and vote data in the request body.
2. 2. Retrieve all votes for an event item using `Votes_GetAll` with the `Client` and `EventItemId` path parameters.
3. 3. Retrieve a specific vote using `Votes_Get` with the `Client`, `EventItemId`, and `VoteId` path parameters.
4. 4. Update an existing vote using `Votes_Put` with the `Client`, `EventItemId`, and `VoteId` path parameters and updated vote data in the request body.
5. 5. Delete a vote using `Votes_Delete` with the `Client`, `EventItemId`, and `VoteId` path parameters.

## Rules

- Authentication headers are required for all operations as indicated by the secure server URL.
- The `Votes_Post` operation is not idempotent as it creates new resources.
- The `Votes_Put` and `Votes_Delete` operations are idempotent as they modify or delete specific resources.
- Error handling should account for invalid `Client`, `EventItemId`, or `VoteId` parameters.
