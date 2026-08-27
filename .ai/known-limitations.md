# Known Limitations & Exclusions

This document records limitations discovered during Solution Book synchronization. It is evidence-driven: absence of an implementation artifact is not treated as proof that a capability can never exist.

## Current audit findings

### 1. No individual `.agents/` directory exists in this repository

The repository itself is `slaveHQ-bot/.agents`, and the current tree contains the global `.ai/` documentation layer, templates, tasks and human-facing docs. No nested `.agents/` directory or individual agent-definition files were found in the current `main` tree.

**Impact:** the current audit can compare the canonical agent registry, taxonomy and protocol documents, but cannot truthfully claim that it has synchronized capabilities from per-agent definition files that are not present.

**Required follow-up:** when individual agent definition files are introduced, the audit must inspect them and compare them against `.ai/agent-capability-registry.md`, `.ai/capabilities/`, `.ai/agent-system.md` and the roadmap.

### 2. Capability documents describe target design, not implementation status

The registry and full-stack taxonomy explicitly describe conceptual capabilities. They do not establish that a capability is implemented, wired or production-ready.

Use the status lifecycle:

`planned` → `discovered` → `partial` → `wired` → `tested` → `production-ready`

Only repository evidence, tests/evals or task history may promote a capability to a stronger status.

### 3. Conceptual agent lifecycle is not a concrete API contract

The agent system defines a conceptual lifecycle (`capabilities`, `health`, `plan`, `execute`, `observe`, `evaluate`, `cancel`) but explicitly requires concrete method names to be discovered from the target implementation before coding.

**Exclusion:** do not generate runtime interfaces solely from these documentation method names.

### 4. MCP behavior must remain version-aware

MCP transport/protocol behavior must be tracked against the current official specification and actual adapters. Historical protocol details must not be frozen as permanent invariants.

### 5. Browser and scraping capabilities are permission- and policy-bound

Browser automation may require semantic, accessibility, visual or protocol adapters depending on the site and environment. Scraping must account for applicable robots directives, terms, permissions, rate limits and technical constraints.

### 6. Media capabilities are conditional

Image, video and audio generation/editing capabilities are target capabilities and may depend on available local tools, providers, hardware and adapters. Generation alone is not sufficient; visual/media verification is part of the intended completion path.

### 7. Self-healing and self-evolution are bounded

Self-healing is limited to permissioned, auditable and bounded recovery. Self-modification of executable code is a separate controlled development workflow and cannot bypass authorization, safety, tests or review.

### 8. Cloud connectivity is optional

SLAVE must remain usable locally. Cloud/remote instances are optional, user-controlled extensions and must not become a silent dependency for normal local operation.

### 9. No automatic 10-minute documentation loop is established by this repository

The documentation standard defines synchronization behavior, but this repository currently contains no verified scheduler/agent runner that can autonomously perform a semantic audit every 10 minutes. A future implementation must use an actual execution mechanism and record audit evidence; documentation text alone does not create an automation.

## Synchronization rule

When a future audit discovers a new capability, limitation or terminology in an individual agent definition:

1. verify the source file and implementation evidence
2. deduplicate against the registry and taxonomy
3. reconcile terminology with the roadmap and architecture
4. update the smallest appropriate `.ai/` document
5. update this limitations document when a constraint is discovered
6. record evidence in the relevant task ledger
7. commit the synchronized documentation

Do not convert aspirational language into implementation claims.
