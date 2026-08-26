---
name: docs-on-demand
description: Use only when blocked by uncertainty about an external library or API such as dbt, DuckDB, Polars, Airflow, or Terraform. Retrieve only the specific documentation needed to proceed.
---

# Documentation lookup

Documentation is expensive. Use it only when local evidence is insufficient.

Before using Context7:
1. Inspect the relevant code and exact error.
2. Prefer installed CLI help, existing project examples, schemas, and local configuration.
3. Identify one concrete API uncertainty.

Use Context7 only when:
- the failure depends on an external library API;
- local code, help output, and examples did not establish the answer;
- you can formulate one specific API question.

Do not use Context7 for SQL semantics, business rules, survey interpretation,
shell commands, debugging logic, or repository navigation. Local evidence
answers those.

When querying:
- Ask about exactly one concept.
- Include the library version when known.
- Prefer the exact library ID if already known.
- Do not request general tutorials or broad documentation.
- Do not repeat essentially the same lookup.
- Normally perform at most one documentation lookup sequence per task.

Good:
"dbt-core 1.9 incremental models: unique_key behavior with delete+insert on DuckDB"

Bad:
"How does dbt work?"

After retrieving documentation:
1. Extract only the fact needed for the current decision.
2. Apply it.
3. Verify by execution.
4. Do not fetch more documentation unless verification exposes a new API uncertainty.
