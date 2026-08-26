---
name: benchmark-core
description: Use for benchmark engineering tasks requiring a verified change.
---

# Solve efficiently

1. Read the task and named files first.
2. Convert every requirement into a concrete, checkable invariant --- not
   just the one you already have evidence for.
3. Run/reproduce the current behavior early.
4. Inspect actual data/output rather than guessing.
5. Make the smallest relevant change.
6. Run the real workflow/check afterward.
7. If no test exists, create a focused check from the requirements.
8. Check off every invariant from step 2 individually. A fix that resolves
   the symptom you noticed can still leave another one unverified.
9. For incremental or destructive work, check idempotence.
10. Use exact failure output as evidence for the next attempt.
11. Do not repeatedly explore after enough evidence exists to act.

Prefer local docs over external docs.
Use external documentation only for one concrete API uncertainty.
Do not finish without executable verification of every invariant.
