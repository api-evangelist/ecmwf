---
name: ecmwf-retrieve-dataset
title: Retrieve data from a Data Store dataset
description: Describe a dataset process, validate the request against its constraints, estimate cost, submit the
  retrieval job, poll it and download the result.
api: openapi/ecmwf-data-stores-processing-openapi.yml
operations:
- GetProcess_processes__process_id__get
- apply_constraints_processes__process_id__constraints_post
- estimate_cost_processes__process_id__costing_post
- PostProcessExecution_processes__process_id__execution_post
- GetJob_jobs__job_id__get
- GetJobResults_jobs__job_id__results_get
generated: '2026-10-18'
method: generated
source: Grounded in openapi/ecmwf-data-stores-processing-openapi.yml; every operationId verified verbatim in the
  spec. Auth per https://cds.climate.copernicus.eu/how-to-api.
---

# Retrieve data from a Data Store dataset

Describe a dataset process, validate the request against its constraints, estimate cost, submit the retrieval job, poll it and download the result.

## Steps

1. `GetProcess_processes__process_id__get` — read the process (dataset id, e.g. as listed in the catalogue) to learn its inputs.
2. `apply_constraints_processes__process_id__constraints_post` — send the partial selection; keep only values the response reports as valid.
3. `estimate_cost_processes__process_id__costing_post` — check the request cost against limits before submitting.
4. `PostProcessExecution_processes__process_id__execution_post` — submit `{"inputs": {...}}`; a `201` returns the job with its `jobID`.
5. `GetJob_jobs__job_id__get` — poll until the status is terminal (successful / failed / dismissed). Back off between polls.
6. `GetJobResults_jobs__job_id__results_get` — read the result asset href and download it.

Rules: steps 2-6 require the `PRIVATE-TOKEN` header. If the dataset licence has not been accepted, accept it first (see `ecmwf-accept-dataset-licences`). Submitting is not idempotent — each POST creates a new job, so do not blindly retry a timed-out submit; list jobs first. Validation failures return `422`.
