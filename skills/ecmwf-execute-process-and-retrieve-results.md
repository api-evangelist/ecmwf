---
name: ecmwf-execute-process-and-retrieve-results
description: Execute a climate data process and retrieve the job results.
api: openapi/ecmwf-data-stores-catalogue-openapi.yml
operations:
- GetProcesses_processes_get
- PostProcessExecute_processes__process_id__execute_post
- GetJob_jobs__job_id__get
- GetJobResults_jobs__job_id__results_get
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/ecmwf-data-stores-catalogue-openapi.yml ; every operationId checked against the contract
---

# ecmwf-execute-process-and-retrieve-results

Execute a climate data process and retrieve the job results.

## Steps

1. 1. Get available processes using `GetProcesses_processes_get` to list processes
2. 2. Execute a specific process using `PostProcessExecute_processes__process_id__execute_post` with the process_id parameter
3. 3. Check job status using `GetJob_jobs__job_id__get` with the job_id parameter
4. 4. Retrieve job results using `GetJobResults_jobs__job_id__results_get` with the job_id parameter

## Rules

- Use appropriate authentication headers as required by the specific server endpoint
- Job execution operations are not idempotent - each call creates a new job
- Use pagination parameters when listing processes or jobs if response is large
- Check job status before retrieving results as jobs may still be processing
