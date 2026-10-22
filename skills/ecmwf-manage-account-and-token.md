---
name: ecmwf-manage-account-and-token
description: Manage ECMWF account data and personal API tokens for accessing climate data services.
api: openapi/ecmwf-data-stores-profiles-openapi.yml
operations:
- get_account_data_account__get
- update_account_account__patch
- Get_personal_API_Token_account_pat_get
- Generate_a_new_personal_API_Token_account_pat_put
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/ecmwf-data-stores-profiles-openapi.yml ; every operationId checked against the contract
---

# ecmwf-manage-account-and-token

Manage ECMWF account data and personal API tokens for accessing climate data services.

## Steps

1. 1. Get account data using `get_account_data_account__get` operation
2. 2. Update account information using `update_account_account__patch` operation with fields from the request body
3. 3. Get personal API token using `Get_personal_API_Token_account_pat_get` operation
4. 4. Generate a new personal API token using `Generate_a_new_personal_API_Token_account_pat_put` operation

## Rules

- Use appropriate authentication headers as required by the specific operation
- Account creation requires POST request to /account/ endpoint
- Personal API token operations require proper authentication
- Account updates use PATCH method for partial modifications
