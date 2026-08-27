# SLAVE GitHub Workflow

## Lifecycle

```text
GitHub Issue
   ↓
Approved scope
   ↓
TASK-[ID].md in tasks/active/
   ↓
Working branch
   ↓
Agent execution + verification
   ↓
Pull Request
   ↓
Review + CI
   ↓
Merge
   ↓
TASK-[ID].md → tasks/archive/
```

## Issue → Task

Approved issues should become deterministic task files. The task must define objective, context, boundaries, sequential steps, verification, and completion criteria.

## Branches

Use one working branch per task. Keep unrelated changes out of the branch.

## Pull requests

The PR description should contain:

- objective
- scope
- changed areas
- completed task checklist copied from the task ledger
- verification commands and results
- integration/wiring checks
- documentation changes
- known limitations

## Doc Sync

If a PR changes architecture, package ownership, contracts, directories, configuration, integrations, or important behavior, the relevant `.ai/` and `AGENT.md` documentation must be updated in the same change.

## Archiving

After merge, move the completed task file from `tasks/active/` to `tasks/archive/`. Preserve the completed checklist and verification evidence.

## Never

- merge unverified work
- claim CI passed without evidence
- delete task history after merge
- silently introduce structural changes without documentation
