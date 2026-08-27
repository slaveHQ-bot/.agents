# Task System

`tasks/active/` contains executable work currently in progress.

`tasks/archive/` contains completed historical tasks.

Every task uses `.ai/templates/task-spec-template.md` and must contain:

- objective
- context loading requirements
- current-state findings
- boundaries/invariants
- sequential execution steps
- verification commands
- integration/wiring checks
- completion evidence

Agents must not skip verification gates.
