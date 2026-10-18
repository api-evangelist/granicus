---
name: granicus-manage-person
description: Create, retrieve, update, and delete Person records in the Granicus Legistar system.
api: openapi/granicus-legistar-openapi.yml
operations:
- Persons_Post
- Persons_Get
- Persons_Put
- Persons_Delete
- Persons_GetAll
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/granicus-legistar-openapi.yml ; every operationId checked against the contract
---

# granicus-manage-person

Create, retrieve, update, and delete Person records in the Granicus Legistar system.

## Steps

1. 1. Create a new Person using `Persons_Post` with the required Person fields in the request body
2. 2. Retrieve a specific Person using `Persons_Get` with the `PersonId` path parameter
3. 3. Update an existing Person using `Persons_Put` with the `PersonId` path parameter and updated fields in the request body
4. 4. Delete a Person using `Persons_Delete` with the `PersonId` path parameter
5. 5. List all Persons using `Persons_GetAll` to retrieve the complete collection

## Rules

- All operations require the Client path parameter in the URL
- Use appropriate HTTP methods: POST for creation, GET for retrieval, PUT for updates, DELETE for deletion
- PersonId path parameter is required for single Person operations (GET, PUT, DELETE)
- Follow standard REST conventions for resource management
