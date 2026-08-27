# Known Limitations & Exclusions

This document records limitations discovered during Solution Book synchronization. It is evidence-driven: absence of an implementation artifact is not treated as proof that a capability can never exist.

## Current audit findings

### 1. No individual agent-definition files exist in this repository

The current `main` tree contains the global `.ai/` Solution Book, templates, human-facing documentation and task index, but no individual specialist-agent definition files.

**Impact:** this repository can define the canonical taxonomy, registry and governance rules, but it cannot claim synchronization from per-agent definition files until those files exist inside the permitted audit scope.

**Required follow-up:** when agent definitions are introduced into the permitted scope, inspect them and reconcile their capabilities, limitations and terminology against the registry, taxonomy, agent system and roadmap.

### 2. Capability documents describe target design, not implementation status

The registry and capability matrix are conceptual contracts. They do not establish that a capability is implemented, wired or production-ready.

Use the status lifecycle:

`planned` → `discovered` → `partial` → `wired` → `tested` → `production-ready`

Only repository evidence, tests/evals or task history may promote a capability to a stronger status.

### 3. No implementation verification is possible from this documentation repository alone

The Solution Book deliberately does not treat its own architectural descriptions as implementation evidence. Any capability requiring code, runtime, integration, UI, persistence, browser, desktop, scheduler or provider verification remains `UNVERIFIED` until evidence is available within the explicitly permitted implementation-evidence scope.

**Exclusion:** never convert a roadmap item, registry entry, class/interface example or expected verification command into a claim that the capability exists.

### 4. Conceptual agent lifecycle is not a concrete API contract

The agent system defines a conceptual lifecycle (`capabilities`, `health`, `plan`, `execute`, `observe`, `evaluate`, `cancel`) but explicitly requires concrete method names to be discovered from the target implementation before coding.

**Exclusion:** do not generate runtime interfaces solely from these documentation method names.

### 5. Task hierarchy is specified but `tasks/active/` and `tasks/archive/` were absent from the current tree

`tasks/README.md` specifies deterministic active and archived task ledgers, but the current repository tree contains only `tasks/README.md` and `tasks/ROADMAP.md`.

**Impact:** the governance rule is documented, but the expected physical hierarchy was not fully represented.

**Required follow-up:** create and use the active/archive directories when deterministic execution ledgers are introduced; do not use checkboxes as evidence unless the corresponding task contains actual verification results.

### 6. Duplicate known-limitations sources previously existed

Both root `known-limitations.md` and `.ai/known-limitations.md` contained substantially overlapping limitation content. This creates two possible sources of truth.

**Resolution:** `.ai/known-limitations.md` is the canonical Solution Book limitations document. The root duplicate should not be recreated.

### 7. MCP behavior must remain version-aware

MCP transport, authorization, tasks and extension behavior changes over time. Historical protocol details must not be frozen as permanent invariants. The current benchmark references the 2026-07-28 MCP specification release and should be refreshed when protocol changes materially affect SLAVE contracts.

### 8. Browser and scraping capabilities are permission- and policy-bound

Browser automation may require semantic, accessibility, visual or protocol adapters depending on the site and environment. Scraping must account for applicable robots directives, terms, permissions, rate limits and technical constraints.

### 9. Media capabilities are conditional

Image, video and audio generation/editing capabilities are target capabilities and may depend on available local tools, providers, hardware and adapters. Generation alone is not sufficient; visual/media verification is part of the intended completion path.

### 10. Self-healing and self-evolution are bounded

Self-healing is limited to permissioned, auditable and bounded recovery. Self-modification of executable code is a separate controlled development workflow and cannot bypass authorization, safety, tests or review.

### 11. Cloud connectivity is optional

SLAVE must remain usable locally. Cloud/remote instances are optional, user-controlled extensions and must not become a silent dependency for normal local operation.

### 12. No automatic 10-minute documentation loop is established by this repository

The documentation standard defines synchronization behavior, but this repository contains no verified scheduler/agent runner that autonomously performs a semantic audit every 10 minutes. Documentation text alone does not create an automation.

### 13. Competitive benchmark evidence is time-sensitive

Competitor capabilities, limits, pricing, protocols and product availability change rapidly. Competitive classifications must include a source date and should be refreshed periodically. Competitors are benchmarks, not automatic SLAVE requirements.

## Synchronization rule

When a future audit discovers a new capability, limitation or terminology:

1. verify the source file and permitted implementation evidence
2. deduplicate against the registry and taxonomy
3. reconcile terminology with the roadmap and architecture
4. update the smallest appropriate `.ai/` document
5. update this limitations document when a constraint is discovered
6. record evidence in the relevant task ledger
7. commit only synchronized documentation with a precise `docs:` message

Do not convert aspirational language into implementation claims.
