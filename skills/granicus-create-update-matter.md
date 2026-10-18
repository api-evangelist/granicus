---
name: granicus-create-update-matter
description: Create a new matter or update an existing one in the Granicus Legistar system.
api: openapi/granicus-legistar-openapi.yml
operations:
- Matters_Get
- Matters_Put
- Matters_Post
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/granicus-legistar-openapi.yml ; every operationId checked against the contract
---

# granicus-create-update-matter

Create a new matter or update an existing one in the Granicus Legistar system.

## Steps

1. 1. Check if a matter exists by calling `Matters_Get` with the MatterId parameter
2. 2. If the matter exists, update it by calling `Matters_Put` with the MatterId parameter and updated matter data
3. 3. If the matter does not exist, create it by calling `Matters_Post` with new matter data

## Rules

- Use the Client path parameter in all requests
- Include authentication headers as required by the API
- Handle 404 errors when MatterId does not exist
