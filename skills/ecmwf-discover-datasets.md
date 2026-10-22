---
name: ecmwf-discover-datasets
title: Discover datasets in the catalogue
description: Search the STAC catalogue for datasets, read a collection, its licences and its changelog.
api: openapi/ecmwf-data-stores-catalogue-openapi.yml
operations:
- Datasets_Search_datasets_post
- Get_Collection_collections__collection_id__get
- licence_details_vocabularies_licences__licence_uid__get
- list_changelog_by_id_collections__collection_id__messages_changelog_get
generated: '2026-10-18'
method: generated
source: Grounded in openapi/ecmwf-data-stores-catalogue-openapi.yml; every operationId verified verbatim in the
  spec. Auth per https://cds.climate.copernicus.eu/how-to-api.
---

# Discover datasets in the catalogue

Search the STAC catalogue for datasets, read a collection, its licences and its changelog.

## Steps

1. `Datasets_Search_datasets_post` — search datasets by text/keywords.
2. `Get_Collection_collections__collection_id__get` — read the chosen STAC Collection (description, extent, links, licences).
3. `licence_details_vocabularies_licences__licence_uid__get` — read each licence the collection references.
4. `list_changelog_by_id_collections__collection_id__messages_changelog_get` — check recent changes to the dataset.

Rules: catalogue operations take no credentials. The same paths exist on cds.climate.copernicus.eu, ads.atmosphere.copernicus.eu and ewds.climate.copernicus.eu — pick the store that hosts the dataset.
