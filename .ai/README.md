# Solution Book

The `.ai/` directory is the global context layer for SLAVE agents.

## Operating principle

The Solution Book is the architectural source of truth, but it must remain hierarchical and evidence-based. It is never a substitute for inspecting the real implementation repository.

## Loading order

1. Read the complete active task.
2. Read this index.
3. Read the relevant sections of `monorepo-map.md`.
4. Read applicable `core-invariants.md` rules.
5. Read applicable `api-contracts.md` sections.
6. Read the relevant architecture/orchestration/capability documents.
7. Read every applicable local `AGENT.md` from repository root to target package.
8. Inspect the actual implementation, callers, dependencies, tests and connections.
9. Only then design and modify code.

## Documents

| Document | Purpose |
|---|---|
| `monorepo-map.md` | Routing map from capabilities to code locations |
| `core-invariants.md` | Non-negotiable architecture, privacy and safety rules |
| `api-contracts.md` | Boundaries between UI, core, gateway, agents, tools and integrations |
| `architecture.md` | Core product architecture |
| `development-roadmap.md` | Long-term implementation roadmap and phase definitions |
| `agent-system.md` | Master SLAVE and specialist agent model |
| `agent-capability-registry.md` | Target specialist/capability inventory |
| `orchestration.md` | Planning, delegation, execution and recovery model |
| `integration-strategy.md` | Browser, MCP, plugin, desktop and cloud integration rules |
| `self-evolution.md` | Evaluation, learning, self-healing and controlled self-evolution |
| `security-and-permissions.md` | Permission, safety, secret and audit model |
| `capability-matrix.md` | Capability inventory and expected verification |
| `daily-development-protocol.md` | Meaning of the user's short `Develop:` command |
| `implementation-protocol.md` | Mandatory engineering workflow |
| `testing-strategy.md` | Test, build and integration verification policy |
| `documentation-rules.md` | Rules for keeping docs synchronized |
| `known-limitations.md` | Verified documentation, capability and automation constraints |
| `github-workflow.md` | Issue → task → branch → PR → archive lifecycle |
| `agent-protocol.md` | Constrained agent initialization and execution instructions |
| `templates/` | Reusable task, agent, issue, PR and report templates |

## Daily development model

The preferred user command is:

```text
Develop: <objective>
```

The agent must automatically inspect the repository, determine where the work belongs, create/select a deterministic task, assign appropriate specialists, execute step-by-step, test, repair, audit connections, build and synchronize documentation.

The user should not have to provide repository paths unless the requirement itself is ambiguous.

## Agent-definition synchronization

When individual agent definition files exist, they are audit inputs rather than independent sources of truth. Their capabilities, limitations and terminology must be reconciled against the registry, taxonomy, architecture and roadmap. Duplicate or conflicting definitions must not be copied blindly.

The audit must distinguish:

- aspirational capability
- discovered implementation
- partially wired capability
- tested capability
- production-ready capability
- explicit limitation or exclusion

See `known-limitations.md` for constraints discovered in the current repository.

## Important

This repository defines the reusable SLAVE development standard. A real SLAVE code repository must continuously populate its Solution Book with verified facts from that repository. Never invent paths, APIs, services, dependencies, integrations or implementation status merely because an example appears in these documents.
