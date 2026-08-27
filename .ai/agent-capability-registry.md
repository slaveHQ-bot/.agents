# SLAVE Agent Capability Registry

The registry is the conceptual contract for discoverable specialists and tools. The implementation should derive runtime registrations from canonical code, not from this document alone.

## Master

`master.slave`

Primary orchestrator. Plans, delegates, executes, evaluates, repairs and reports.

## Specialists

- `browser.slave` — browser/computer web operations
- `research.slave` — research and evidence
- `scraper.slave` — structured web extraction
- `repo.slave` — coding/repository engineering
- `data.slave` — data workflows
- `finance.slave` — finance workflows
- `creative.slave` — creative orchestration
- `image.slave` — image workflows
- `video.slave` — video workflows
- `audio.slave` — audio workflows
- `documents.slave` — document workflows
- `reports.slave` — report generation
- `qa.slave` — testing and quality
- `sales.slave` — sales workflows
- `advisor.slave` — decision support
- `assistant.slave` — personal assistance
- `automation.slave` — scheduled/event workflows

## Common metadata

Each agent registration should be able to describe:

- stable identifier
- human name
- purpose
- capabilities
- required tools
- supported input/output types
- permissions
- model requirements
- health
- version
- owner/package
- evaluation status

## Extensibility

New specialist agents should be added by implementing the common agent contract, registering capabilities, adding local `AGENT.md` rules where needed, adding tests/evals, and updating the Solution Book.

Do not fork the entire runtime for a new domain unless an architecture decision explicitly requires it.
