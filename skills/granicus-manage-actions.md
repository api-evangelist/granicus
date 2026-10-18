---
name: granicus-manage-actions
description: Create, read, update, and delete Actions in the Granicus system.
api: openapi/granicus-legistar-openapi.yml
operations:
- Actions_Post
- Actions_Get
- Actions_Put
- Actions_Delete
- Actions_GetAll
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/granicus-legistar-openapi.yml ; every operationId checked against the contract
---

# granicus-manage-actions

Create, read, update, and delete Actions in the Granicus system.

## Steps

1. 1. Create a new Action using `Actions_Post` with the required fields in the request body
2. 2. Retrieve a specific Action using `Actions_Get` with the `ActionId` path parameter
3. 3. Update an existing Action using `Actions_Put` with the `Id` path parameter and updated fields in the request body
4. 4. Delete an Action using `Actions_Delete` with the `Id` path parameter
5. 5. List all Actions using `Actions_GetAll` to view the complete collection

## Rules

- All operations require the `Client` path parameter in the URL
- The `Actions_Put` and `Actions_Delete` operations use `Id` as the path parameter while `Actions_Get` uses `ActionId`
- Operations follow standard HTTP methods: POST for create, GET for read, PUT for update, DELETE for delete
- The base URL is https://webapi.legistar.com/v1/{Client}
