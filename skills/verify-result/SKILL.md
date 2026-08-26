---
name: verify-result
description: Use for every task that changes code or configuration. MUST verify the requested behavior by execution and explicit task invariants before finishing; a successful command alone is not proof. Never dump large files into context.
---

# Verify the result

Before editing, turn the task requirements into 2-5 observable invariants.

After editing:

1. Run the real workflow, script, parser, query, or validator.
2. Check the requested outcome, not just the exit code.
3. If the task gives counts, totals, uniqueness, freshness, latest/current,
   idempotence, or security requirements, verify them explicitly.
4. If there is no visible test suite, construct small independent checks.
5. If new documentation is read after an edit, re-evaluate the implementation
   and rerun verification before finishing.

Never finish immediately after an edit.

For unknown-size files:
- never use cat/head/tail on CSV, JSON, parquet or large logs before checking size;
- inspect schema/columns and narrowly selected records instead;
- keep command output small.

Examples:

Data reconciliation:
source row count == output represented row count
source amount sum == output amount sum

Incremental/stateful:
run twice and check the second execution is correct/idempotent

Airflow:
verify imports and DAG parsing

Terraform/OpenTofu:
run fmt/validate when available
