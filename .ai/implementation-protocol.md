# SLAVE Implementation Protocol

Every coding-agent implementation follows this lifecycle.

## Phase 0 — Context loading

- Read the complete active task.
- Read `.ai/README.md`.
- Read relevant `monorepo-map.md` entries.
- Read relevant `core-invariants.md` rules.
- Read relevant `api-contracts.md` sections.
- Read every applicable local `AGENT.md` from repository root to target package.

## Phase 1 — Reconnaissance

Before editing:

1. Inspect repository structure.
2. Locate the requested feature.
3. Search for existing implementations.
4. Search interfaces, types, schemas and contracts.
5. Trace callers and consumers.
6. Trace UI/desktop/IPC/RPC/API connections.
7. Trace persistence and configuration.
8. Trace tests.
9. Identify duplicated, dead, broken, or partially wired implementations.
10. Record the implementation path in the task ledger.

## Phase 2 — Design

Define the smallest change that satisfies the requirement while preserving existing architecture. Prefer extending canonical implementations over creating parallel systems.

Explicitly identify:

- files to modify
- files to add
- files that must not change
- interfaces/contracts affected
- migrations required
- tests required
- documentation that must be synchronized

## Phase 3 — Implementation

Implement sequentially. Keep changes scoped. Preserve compatibility unless the task explicitly authorizes a breaking change.

## Phase 4 — Wiring

Verify the complete path, not only compilation:

**UI/input → boundary → service/core → provider/tool → state/output → UI/result**

Check registration, dependency injection, event handlers, routes, IPC/RPC commands, permissions, configuration, persistence, and error handling as applicable.

## Phase 5 — Verification

After each execution step, run its specified verification. Do not continue when verification fails. Attempt diagnosis and repair up to the task's allowed limit (default: 2 attempts), then stop and request clarification.

After all steps:

- run targeted tests
- run integration tests
- run typecheck/lint where applicable
- run production build
- perform a final connection/wiring review

## Phase 6 — Documentation

Update `.ai/` and local `AGENT.md` whenever implementation changes architecture, contracts, ownership, paths, workflows, configuration, or important behavior.

## Phase 7 — Completion

Update every task checkbox with the actual verification result. Never claim a command passed unless it was actually executed and passed.

The final report must include changed files, tests/builds run, integration verification, known limitations, and documentation synchronized.
