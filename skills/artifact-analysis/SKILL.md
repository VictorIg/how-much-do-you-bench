---
name: artifact-analysis
description: MUST use when parsing Harbor jobs, trajectories, run directories, logs, benchmark exports, or similar file trees. Read local format docs before implementation and account for retries, canaries/non-exercises, missing files, and multiple structural examples.
---

# Artifact analysis

The local docs define the file format.

Before implementation:

1. List the documentation files.
2. Read format/layout/reward/test-output documentation before coding.
3. Inspect at least two structurally different examples when available.
4. Determine the canonical identity of one logical exercise/run.
5. Determine how retries are represented.
6. Determine which directories are metadata/canaries/logs rather than exercises.
7. Determine semantics of missing reward/output files.

Do not infer meaning solely from directory names.

Before finishing, create focused edge-case checks for:
- a retry;
- a non-exercise directory/canary;
- missing reward;
- missing output;
where those concepts exist in the documented format.

If reading a later documentation file changes your understanding,
update the implementation and rerun verification.
