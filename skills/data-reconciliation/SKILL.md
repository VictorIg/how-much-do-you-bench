---
name: data-reconciliation
description: MUST use when a task mentions revenue/totals, duplicates, joins, latest/current records, fanout, SCD, incremental models, warehouse reconciliation, missing records, or one-row-per-key requirements. Establish source grain and verify counts/sums after execution.
---

# Data reconciliation

Before changing code, establish:

- source grain;
- intended output grain;
- unique/business key;
- whether dimension/history tables contain multiple rows per key;
- meaning of "latest", "current", or "most recent";
- required treatment of unmatched records.

Do not fix join fanout using arbitrary dropDuplicates/deduplication unless
the business rule actually says any row is acceptable.

When "current/latest" matters, determine the ordering/version column and select
the correct row deterministically.

For joins, explicitly consider:
- one-to-many fanout;
- many-to-many fanout;
- inner-join row loss;
- null/unmatched keys.

After running the pipeline, independently reconcile relevant invariants:

- source event count vs represented event count;
- source amount/revenue sum vs output total;
- uniqueness at the required grain;
- unmatched records handled as required.

A successful pipeline execution is not verification.
