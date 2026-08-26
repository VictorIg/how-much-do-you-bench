---
name: benchmark-core
description: Use for engineering benchmark tasks. Solve from local evidence, make minimal changes, and verify by execution.
---

# Benchmark workflow

Produce a verified working result.

## 1. Establish the contract

Identify:
- required end state;
- files/interfaces that must remain unchanged;
- observable invariants;
- cheapest executable verification.

## 2. Inspect local evidence first

Prefer, in order:
1. task instruction;
2. named implementation files;
3. local docs/codebooks;
4. actual input data/schema;
5. existing project examples/configuration;
6. external documentation only if an API remains uncertain.

Do not broadly read the repository without a reason.

## 3. Reproduce

Run the supplied command/script/test when practical.

For data tasks, inspect actual outputs rather than reasoning only from code.

## 4. Diagnose

Form one concrete hypothesis from observed evidence.

Pay particular attention to:
- data grain and uniqueness;
- NULL behavior;
- join multiplicity;
- boundary conditions;
- repeated-run/idempotence behavior;
- exact output/interface requirements.

## 5. Change

Make the smallest relevant modification.
Preserve existing interfaces and unrelated behavior.

## 6. Verify

Run the real workflow after editing.

If no visible tests exist, construct focused checks directly from
the requirements.

For stateful/incremental/destructive operations, test repeated execution
when relevant.

Never claim completion from code inspection alone.

## 7. Recover

If verification fails, use the exact result as new evidence.
Do not repeat an unchanged failed approach.
