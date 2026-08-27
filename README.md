# SLAVE Agent Solution Book

The canonical agent-development and architecture governance repository for the SLAVE ecosystem.

SLAVE is intended to become a local-first, open-source, BYOK AI operating environment with one **Master SLAVE** coordinating specialized agents, tools, integrations and automations.

## The daily workflow

The user should be able to say:

```text
Develop: <objective>
```

The agent then reads the Solution Book, inspects the actual target repository, finds existing implementations, creates/selects the required task ledger, assigns specialist agents, implements, wires, tests, repairs, builds and synchronizes documentation.

The user should not need to know the repository's internal paths.

## Target ecosystem

```text
Master SLAVE
├── Browser SLAVE
├── Research SLAVE
├── Scraper SLAVE
├── Coding / Repo SLAVE
├── Data SLAVE
├── Finance SLAVE
├── Creative SLAVE
│   ├── Image SLAVE
│   ├── Video SLAVE
│   └── Audio SLAVE
├── Documents SLAVE
├── Reports SLAVE
├── QA SLAVE
├── Sales SLAVE
├── Advisor SLAVE
├── Personal Assistant SLAVE
└── Automation SLAVE
```

The platform also targets browser/computer control, filesystem and shell capabilities, MCP and plugins, scheduling, memory, self-evaluation, bounded self-healing and controlled learning/self-evolution.

## Documentation architecture

- `.ai/` — global Solution Book
- local `AGENT.md` — package/application rules in implementation repositories
- `tasks/active/` — executable work ledgers
- `tasks/archive/` — completed task history
- `docs/` — human-facing documentation
- `.github/` — GitHub workflow standards

## Start here

1. `.ai/README.md`
2. `.ai/daily-development-protocol.md`
3. `.ai/development-roadmap.md`
4. `.ai/agent-system.md`
5. `.ai/orchestration.md`
6. `.ai/implementation-protocol.md`

## Core engineering rule

**Never implement by guessing.** Analyze the existing codebase first. Search for canonical implementations and all affected connections. Reuse/modify rather than duplicate. Wire the complete path. Test it. Build it. Fix failures. Record evidence. Synchronize the Solution Book.
