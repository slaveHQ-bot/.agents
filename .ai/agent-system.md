# SLAVE Agent System

## 1. Master SLAVE

Master SLAVE is the primary user-facing agent and orchestrator. It owns the task lifecycle, not every domain implementation.

Responsibilities:

- understand user intent
- load relevant context
- retrieve memory
- plan and decompose objectives
- select specialists
- select tools
- enforce permissions and safety
- coordinate sequential/parallel execution
- observe results
- evaluate outputs
- recover safe failures
- consolidate results
- persist useful knowledge
- report evidence
- schedule future work

Master SLAVE must use common interfaces so specialists remain composable.

## 2. Specialist agents

### Browser SLAVE
Browser navigation, interaction, page state, screenshots, uploads/downloads, CDP/protocol adapters and browser skills.

### Research SLAVE
Search, source retrieval, evidence collection, synthesis, citation/provenance, freshness and contradiction analysis.

### Scraper SLAVE
Structured extraction, pagination, selectors, normalization, deduplication, rate limiting and export. Scraping behavior must respect applicable robots directives, site terms and permission boundaries.

### Coding / Repo SLAVE
Code search, architecture analysis, implementation, testing, builds, repository operations, issue/task/PR workflows and documentation sync.

### Data SLAVE
Data ingestion, cleaning, transformation, analysis, validation, SQL/database operations and reproducible outputs.

### Finance SLAVE
Financial data analysis, reconciliation, models, budgeting, reporting and scenario analysis with explicit source/assumption separation.

### Creative SLAVE
Creative orchestration across Image, Video and Audio specialists plus asset/project management.

### Image SLAVE
Image generation/editing/transformation pipelines and asset verification.

### Video SLAVE
Video planning, generation/editing pipelines, rendering and output verification.

### Audio SLAVE
Audio generation/editing/transcription/synthesis pipelines where supported.

### Documents SLAVE
Document extraction, transformation, creation, formatting and structured content operations.

### Reports SLAVE
Research → analysis → narrative → charts/assets → final report workflows.

### QA SLAVE
Test planning, regression, integration testing, runtime verification, failure reproduction and quality gates.

### Sales SLAVE
Sales research, CRM-like workflows where connected, prospect analysis, outreach preparation and reporting.

### Advisor SLAVE
Decision analysis, options, tradeoffs, planning and evidence-backed recommendations.

### Personal Assistant SLAVE
User-approved personal workflows, reminders, scheduling, communication preparation and recurring routines.

### Automation SLAVE
Scheduled and event-driven workflow execution, dependencies, retries/backoff, concurrency limits, pause/resume/cancel, notifications, execution history and approval gates. Automation remains subject to the same permission, safety and audit boundaries as interactive tasks.

## 3. Common agent contract

Every specialist should expose the same conceptual lifecycle:

```text
capabilities()
health()
plan(task)
execute(task, context)
observe(run)
evaluate(result)
cancel(run)
```

Concrete method names must be discovered from the target implementation before coding.

## 4. Specialist selection

Selection considers:

- task domain
- required tools
- confidence/capability match
- current health
- permissions
- cost/time budget
- dependency requirements
- evaluation history

Master may use multiple specialists when a task crosses domains.

## 5. Parallelism

Independent subtasks may run in parallel. Dependent subtasks must wait for verified prerequisites. Shared mutable resources require concurrency controls.

## 6. Result contract

A specialist result should communicate:

- status
- structured output
- evidence/artifacts
- actions performed
- tools used
- warnings
- errors
- confidence/quality signals where meaningful
- recommended next action

## 7. Capability status

Agent and capability documentation must distinguish target design from verified implementation. Use the lifecycle:

`planned` → `discovered` → `partial` → `wired` → `tested` → `production-ready`

A status must be backed by repository evidence, tests/evals or task history. A capability listed in the registry or taxonomy is not proof that it exists in the implementation.

## 8. No specialist bypass

Specialists cannot bypass Master SLAVE's permission, safety, authentication, secrets, audit or storage boundaries merely because direct access is easier.
