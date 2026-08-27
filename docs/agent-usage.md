# Using the SLAVE Agent Documentation

## For a new implementation

1. Create an issue describing the outcome.
2. Convert the approved issue into `tasks/active/TASK-[ID].md`.
3. Load `.ai/` context and target `AGENT.md` files.
4. Analyze the existing implementation before editing.
5. Execute one task step at a time.
6. Verify every step.
7. Audit every affected connection.
8. Build and test the complete affected surface.
9. Synchronize documentation.
10. Put actual evidence in the task and PR.
11. After merge, archive the task.

## What agents must not do

- Do not start coding from a vague issue without reconnaissance.
- Do not invent file paths or APIs.
- Do not create duplicate services or parallel implementations without architectural justification.
- Do not bypass application boundaries.
- Do not skip integration verification because unit tests pass.
- Do not mark unchecked boxes as complete.
- Do not hide failures.

## Context efficiency

Read only the Solution Book sections relevant to the task, then drill into local `AGENT.md` and source files. This keeps context bounded while preserving architectural correctness.
