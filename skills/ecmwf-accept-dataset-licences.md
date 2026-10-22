---
name: ecmwf-accept-dataset-licences
title: Accept dataset licences
description: Check which licences the account has accepted and accept the ones a dataset requires.
api: openapi/ecmwf-data-stores-profiles-openapi.yml
operations:
- get_licences_account_licences_get
- accept_licence_account_licences__licence_uid__put
- accept_licences_account_licences_patch
generated: '2026-10-18'
method: generated
source: Grounded in openapi/ecmwf-data-stores-profiles-openapi.yml; every operationId verified verbatim in the spec.
  Auth per https://cds.climate.copernicus.eu/how-to-api.
---

# Accept dataset licences

Check which licences the account has accepted and accept the ones a dataset requires.

## Steps

1. `get_licences_account_licences_get` — list licences already accepted by the account.
2. `accept_licence_account_licences__licence_uid__put` — accept a single licence (licence uid comes from the catalogue collection).
3. `accept_licences_account_licences_patch` — accept several licences in one call.

Rules: requires the `PRIVATE-TOKEN` header. PUT on a licence uid is naturally idempotent.
