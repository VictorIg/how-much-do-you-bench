---
name: context-scout
description: Use on unfamiliar tasks when finding the relevant files or data would otherwise require broad repository exploration. Delegate exploration while keeping the main context small.
---

# Context isolation

Use the explore subagent only when locating the relevant implementation would
otherwise require broad repository exploration.

Do not delegate when the task names the relevant files, or the repository is
already small enough to inspect directly. Delegating a trivial task still
costs a full turn and buys nothing.

When broad investigation is genuinely needed:

1. Use the built-in `explore` subagent once.
2. Give it one narrow question.
3. Ask it to identify:
   - relevant files,
   - concrete observed facts,
   - likely verification,
   - important unknowns.
4. Ask for a concise evidence report, not a solution.
5. Do not ask it to reproduce whole files.
6. After receiving the report, read only files required to implement the change.

Do not delegate trivial tasks.

The main agent owns:
- the final diagnosis,
- edits,
- execution,
- verification.
