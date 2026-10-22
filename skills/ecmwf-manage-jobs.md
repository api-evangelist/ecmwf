---
name: ecmwf-manage-jobs
title: Manage retrieval jobs
description: List submitted jobs, check one, read its receipt, and cancel or bulk-delete jobs.
api: openapi/ecmwf-data-stores-processing-openapi.yml
operations:
- GetJobs_jobs_get
- GetJob_jobs__job_id__get
- get_job_receipt_jobs__job_id__receipt_get
- DeleteJob_jobs__job_id__delete
- delete_jobs_jobs_delete_post
generated: '2026-10-18'
method: generated
source: Grounded in openapi/ecmwf-data-stores-processing-openapi.yml; every operationId verified verbatim in the
  spec. Auth per https://cds.climate.copernicus.eu/how-to-api.
---

# Manage retrieval jobs

List submitted jobs, check one, read its receipt, and cancel or bulk-delete jobs.

## Steps

1. `GetJobs_jobs_get` — list the account's jobs.
2. `GetJob_jobs__job_id__get` — inspect one job's status.
3. `get_job_receipt_jobs__job_id__receipt_get` — read the job receipt.
4. `DeleteJob_jobs__job_id__delete` — cancel/delete a single job.
5. `delete_jobs_jobs_delete_post` — delete several jobs in one call.

Rules: all steps require the `PRIVATE-TOKEN` header. Deletion is destructive; confirm job ids from step 1 first.
