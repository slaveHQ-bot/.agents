# SLAVE Full-Stack Agent Capability Taxonomy

## Purpose

This document defines the target capability surface for SLAVE as a full-stack digital worker. It is a capability specification, not proof that every capability is implemented.

## 1. Browser Automation & Web Execution

SLAVE should be able to operate browsers semantically and visually rather than only reading HTML.

### Capabilities
- DOM and accessibility-tree parsing with compact element references.
- Autonomous navigation, clicking, typing, scrolling, tabs, windows, pagination and menus.
- Cookie/consent handling where permitted.
- Complex multi-step forms, date pickers, checkouts, sign-ups and bookings.
- Structured extraction from tables, lists, grids and repeating page structures.
- Scraping into CSV, JSON and other structured outputs.
- Upload/download handling and local file routing.
- Browser screenshots and visual fallback.
- CDP and supported browser automation adapters.

### Routing principle

Prefer semantic/API-level actions when reliable. Use visual interaction as a fallback for controls that cannot be reached semantically.

## 2. Desktop OS & Application Control

SLAVE should operate native applications on supported Linux, macOS and Windows environments through permissioned adapters.

### Capabilities
- Screen observation and visual UI understanding.
- Mouse movement/clicking and keyboard input.
- Clipboard and standard OS shortcuts.
- Window/application discovery and control.
- Accessibility APIs where available.
- Native application workflows.
- Terminal and process execution.
- Filesystem operations.
- Sandboxed/containerized execution for risky or isolated workloads.
- Local applications such as editors, spreadsheets and communication tools through appropriate adapters.

## 3. Protocol, Plugin & API Orchestration

SLAVE should select the most reliable and efficient interface instead of defaulting to visual automation.

### Capability hierarchy

```text
Direct API
  -> MCP / native tool
  -> Browser semantic automation
  -> Desktop accessibility
  -> Vision + mouse/keyboard fallback
```

The router should consider permissions, reliability, latency, cost, availability and task requirements.

### Capabilities
- MCP client/server integration through versioned protocol adapters.
- Plugin discovery, installation, lifecycle and isolation.
- Native API integrations.
- Dynamic tool routing.
- OAuth/session/cookie/token lifecycle management behind the credential boundary.
- User-approved external connections.
- Tool health and capability discovery.

**Protocol note:** MCP behavior must be tracked against the current official specification and implementation. Do not hard-code a historical transport description as a permanent architectural invariant.

## 4. Document Engineering & Coding

### Document capabilities
- PDF parsing and generation.
- OCR and scanned-document extraction.
- Markdown, HTML, XML, JSON, CSV and structured format transformations.
- LaTeX generation and compilation where available.
- Tables, charts, citations and report assembly.
- File validation and output-quality checks.

### Coding capabilities
- Repository reconnaissance.
- Multi-file implementation and refactoring.
- Dependency upgrades.
- Static analysis, type checking and tests.
- Build verification.
- Git operations and task/PR workflow integration.
- Regression diagnosis and repair.

Coding agents must follow the Solution Book and applicable `AGENT.md` rules before modifying source code.

## 5. Image, Video & Audio Workflows

### Image
- Generation and editing.
- Inpainting/outpainting where supported.
- Spatial OCR.
- Image understanding and constraint verification.

### Video
- Generation/editing pipelines where supported.
- Asset assembly.
- Frame/scene inspection.
- Render validation.

### Audio
- Generation and transformation where supported.
- Speech/transcription workflows.
- Audio inspection and output validation.

### Visual verification loop

```text
Generate -> Inspect -> Compare against requirements -> Repair -> Re-inspect
```

The same evaluation pattern should be reusable across media types.

## 6. Cross-Domain Workflows

The architecture must support composed workflows crossing multiple capability domains.

Example:

```text
Research web sources
    -> Browser/Scraper
    -> Download dataset
    -> Filesystem
    -> Data/Python processing
    -> Generate chart
    -> Documents/Report
    -> PDF
    -> QA verification
```

No specialist should need to own the entire workflow. Master SLAVE coordinates the execution graph and delegates individual capabilities.

## 7. Master SLAVE

Master SLAVE is the primary orchestrator. It should:

1. Understand user intent.
2. Load relevant Solution Book context.
3. Inspect available capabilities and tools.
4. Plan the workflow.
5. Delegate specialist work.
6. Route each operation to the best available interface.
7. Track state and dependencies.
8. Verify intermediate and final results.
9. Recover from failures.
10. Report the completed work and evidence.

## 8. Specialist Agents

Target specialists include:

- `browser.slave`
- `research.slave`
- `scraper.slave`
- `repo.slave`
- `data.slave`
- `finance.slave`
- `creative.slave`
- `image.slave`
- `video.slave`
- `audio.slave`
- `documents.slave`
- `reports.slave`
- `qa.slave`
- `sales.slave`
- `advisor.slave`
- `assistant.slave`
- `automation.slave`

Specialists share common runtime contracts, tool permissions, memory interfaces and evaluation infrastructure. They should not duplicate the core runtime unnecessarily.

## 9. Evaluation, Self-Healing & Learning

Every important capability should eventually expose machine-verifiable evaluation criteria.

```text
Plan
 -> Execute
 -> Observe
 -> Evaluate
 -> Pass? ---- yes ---> Continue
    |
    no
    v
 Diagnose -> Repair/Re-plan -> Retry -> Evaluate
```

Self-healing must remain permissioned, auditable and bounded.

Learning should improve strategies, memory, routing and planning. Self-modification of executable code is a separate controlled development workflow and must not bypass authorization, tests or review requirements.

## 10. Capability Status

The capability registry must distinguish target design from actual implementation. Recommended states:

`planned` -> `discovered` -> `partial` -> `wired` -> `tested` -> `production-ready`

Every status claim should be backed by repository evidence, tests or task history.
