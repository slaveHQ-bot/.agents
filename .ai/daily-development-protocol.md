# Daily Development Protocol

## Purpose

The user should be able to give a short instruction such as `Develop: <feature>` without knowing repository paths, implementation details, package names or which specialist should do the work.

The coding agent is responsible for turning that instruction into safe, verifiable implementation work.

## Canonical command

```text
Develop: <objective>
```

Optional forms:

```text
Develop: <objective> --priority high
Develop: <objective> --scope <area>
Develop: continue
Develop: fix current blockers
Develop: audit <area>
```

## Automatic execution

When receiving `Develop:` the agent must:

### 1. Discover

- inspect repository root
- inspect Git state and current branch
- inspect existing Solution Book
- identify active tasks
- identify incomplete/broken work
- inspect relevant local `AGENT.md` files

### 2. Understand

- map the requested capability to `.ai/monorepo-map.md`
- search for existing implementation
- trace interfaces and types
- trace callers/consumers
- trace UI → IPC/RPC/API → core paths
- trace tools/providers/plugins
- trace persistence/configuration
- inspect relevant tests
- identify existing gaps and duplicate systems

Never start by creating files merely because the feature name suggests a path.

### 3. Plan

Create/select a deterministic `tasks/active/TASK-[ID].md`.

The task must state:

- objective
- current-state findings
- context to load
- boundaries/invariants
- implementation steps
- verification after every step
- integration/wiring checks
- final acceptance criteria

For broad requests, decompose into multiple tasks and order dependencies.

### 4. Assign

Master SLAVE chooses the appropriate specialist capability using the orchestration rules. A task may be assigned to one specialist or composed across several.

Examples:

- browser automation → Browser SLAVE
- web evidence → Research SLAVE
- extraction → Scraper SLAVE
- repository/code changes → Coding/Repo SLAVE
- datasets → Data SLAVE
- financial analysis → Finance SLAVE
- image/video/audio → Creative specialists
- document/report generation → Documents/Reports SLAVE
- test and regression work → QA SLAVE

The specialist still follows the same Solution Book and verification protocol.

### 5. Execute

Execute task steps strictly in order. After each step:

1. run the specified verification
2. inspect failure output if failed
3. repair the root cause
4. rerun verification
5. only advance after passing

Default repair budget: two attempts per failed verification unless the task defines another limit.

### 6. Wiring audit

Before completion, verify the whole path:

```text
User/Input
  ↓
UI or Trigger
  ↓
IPC/RPC/API Boundary
  ↓
Master/Service/Agent Runtime
  ↓
Specialist Agent
  ↓
Tool/Provider/Plugin
  ↓
State/Memory/Filesystem
  ↓
Result/Event
  ↓
UI/Caller/Notification
```

Not every feature uses every layer, but every affected connection must be checked.

### 7. Verification

Run applicable:

- targeted tests
- integration tests
- end-to-end tests
- typecheck
- lint/static analysis
- build/package verification
- runtime smoke tests

Never claim a command passed unless it actually ran.

### 8. Documentation sync

Update the relevant Solution Book documents in the same implementation whenever architecture, interfaces, paths, ownership, integrations, configuration, behavior or capability status changes.

Update local `AGENT.md` files when local development rules or boundaries change.

### 9. Report

Return:

- objective
- task ID
- what was found
- what changed
- specialist(s) used
- files changed
- tests/builds executed
- integration/wiring result
- documentation synchronized
- unresolved issues
- next recommended task

## `Develop: continue`

This means:

1. inspect active tasks
2. find the highest-priority unfinished task whose prerequisites are satisfied
3. verify its current state before touching it
4. continue from the actual ledger state
5. never assume a previous agent completed an unchecked step

## `Develop: fix current blockers`

The agent must inspect failed CI/tests/builds/runtime errors, trace root causes, create a repair task if needed, and repair them using the same verification gates.

## `Develop: audit <area>`

Perform an architecture and wiring audit without making speculative changes. Produce findings first. If fixes are clearly required, create follow-up tasks.

## User interaction policy

Do not ask the user to identify files when repository inspection can determine them.

Ask the user only when:

- requirements conflict
- a destructive/high-impact action requires authorization
- a product decision cannot be inferred safely
- required credentials/access are unavailable
- a verification failure remains unresolved after the allowed repair attempts

## Completion rule

The agent must never optimize for appearing productive. It optimizes for verified, integrated, maintainable work.
