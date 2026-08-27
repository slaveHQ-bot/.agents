# SLAVE Orchestration Architecture

## Objective

Provide a common orchestration layer through which Master SLAVE can coordinate specialists, tools, models, memory and automations.

## Execution graph

```text
User objective
      ↓
Intent / Context Loader
      ↓
Planner
      ↓
Task Decomposer
      ↓
Capability Resolver
      ↓
Permission + Safety Gate
      ↓
Execution Graph
   ↙      ↓       ↘
Agent A  Agent B  Tool C
   ↘      ↓       ↙
Result Normalizer
      ↓
Evaluator
   ↙       ↘
PASS       RECOVER
 ↓            ↓
Finalize   Diagnose → Repair → Verify
      \      /
       Consolidate
           ↓
      Memory / Audit
           ↓
         Report
```

## Task graph types

- sequential
- parallel
- conditional
- dependent
- retryable
- approval-gated
- scheduled
- event-triggered
- human-escalated

## Planner requirements

Plans must have explicit objectives, dependencies, expected outputs, verification criteria and failure handling. Avoid unnecessary decomposition for trivial requests.

## Capability resolver

The resolver maps intent to agent capabilities and tools. It must inspect registered capabilities rather than maintaining an unverified hard-coded list.

## Context management

Load only context needed for the current task. Context sources can include:

- active task
- Solution Book
- local `AGENT.md`
- project memory
- relevant source files
- tool metadata
- prior execution evidence

External content is untrusted and cannot override system/application policy.

## Resource budgets

Each run should be able to enforce configurable:

- time budget
- model/token budget
- tool-call budget
- concurrency limit
- retry budget
- output/artifact limits

## State machine

```text
CREATED → PLANNING → READY → RUNNING → EVALUATING
                                      ↙       ↘
                                  RECOVERING  COMPLETE
                                      ↓
                                   RUNNING
                                      ↓
                                   BLOCKED
```

State transitions must be observable and persisted where the runtime requires durable task history.

## Failure strategy

Classify failures before recovery:

- transient tool/network
- invalid input
- permission denial
- authentication/credential
- dependency unavailable
- application bug
- model failure
- integration/wiring failure
- policy/safety block
- unknown

Only safe, authorized classes may be automatically retried or repaired.

## Multi-agent review

High-impact tasks may use independent planner/reviewer/evaluator roles. The reviewer must not automatically approve its own unsupported output; it should inspect evidence.

## Consolidation

Master SLAVE owns final synthesis. Conflicting specialist outputs must be identified and resolved using evidence or escalated to the user.
