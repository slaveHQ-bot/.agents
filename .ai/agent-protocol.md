# SLAVE Agent Protocol

## Mandatory initialization prompt

Use this protocol when assigning a coding agent:

> Your assignment is located in `tasks/active/TASK-[ID].md`. Read this file entirely. Load every context file listed in its Context Loading section, plus applicable `.ai/` and local `AGENT.md` rules. First analyze the existing repository and locate the current implementation and all affected connections. Do not guess or duplicate functionality. Execute the plan strictly step-by-step. Run the verification command after each step and do not continue until it passes. For failures, diagnose and repair the root cause; retry up to 2 times unless the task specifies another limit. If unresolved, stop and ask for clarification. Before completion, test all affected integrations, run the required build, update the task ledger with actual results, and synchronize documentation.

## Agent behavior

The agent must:

- read before editing
- search before creating
- trace before wiring
- verify before advancing
- test integrations, not only isolated code
- preserve invariants
- document structural changes
- report failures honestly

## Completion statement

An agent may say "complete" only when the task's required checks pass, affected connections are verified, and documentation is synchronized.
