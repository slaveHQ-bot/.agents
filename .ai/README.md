# Solution Book

The `.ai/` directory is the global context layer for SLAVE agents.

## Loading order

1. Read the task file completely.
2. Read this index.
3. Read the relevant sections of `monorepo-map.md`.
4. Read applicable `core-invariants.md` rules.
5. Read applicable `api-contracts.md` sections.
6. Read the target package/app `AGENT.md`.
7. Inspect the referenced existing code and its callers/dependencies.
8. Implement only after the architecture is understood.

## Documents

| Document | Purpose |
|---|---|
| `monorepo-map.md` | Routing map from capabilities to code locations |
| `core-invariants.md` | Non-negotiable architectural and safety rules |
| `api-contracts.md` | Contracts between UI, core, gateway, providers, tools and integrations |
| `architecture.md` | Current intended system architecture |
| `implementation-protocol.md` | Mandatory engineering workflow |
| `testing-strategy.md` | Test, build and integration verification policy |
| `documentation-rules.md` | Rules for keeping docs synchronized |
| `github-workflow.md` | Issue → task → branch → PR → archive lifecycle |
| `agent-protocol.md` | Constrained initialization and execution instructions |

## Important

This repository is a reusable standard. A real SLAVE code repository must populate its Solution Book with facts from that codebase. Never invent paths, APIs, services, or dependencies merely because an example contains them.
