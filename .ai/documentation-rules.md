# SLAVE Documentation Rules

## Principle

Documentation is part of the implementation, not an afterthought.

## Hierarchy

Use distributed context:

- root `.ai/` for global architecture and contracts
- local `AGENT.md` for package/application rules
- `tasks/active/` for current execution ledgers
- `tasks/archive/` for completed task history
- `docs/` for human-facing operational/reference documentation

Never create a single giant document intended to contain the entire repository context.

## Update triggers

Update documentation when a change affects:

- directory/package ownership
- architecture
- public/internal contracts
- data flow
- authentication/security boundaries
- persistence/migrations
- configuration
- build/test workflow
- agent behavior
- integration wiring
- supported capabilities

## Accuracy

Document observed repository facts. If something has not been verified, label it as an assumption or investigation item. Do not fabricate paths, APIs, test commands, versions, or integrations.

## Task synchronization

The task ledger must reflect reality. Checkboxes are evidence records, not plans after execution. Include commands and meaningful results.

## Local rules

Each discrete application/package should have an `AGENT.md` describing its stack, entrypoints, ownership, local invariants, testing commands, integration boundaries, and forbidden patterns.

## Review rule

A structural PR without corresponding Solution Book updates should be treated as incomplete.
