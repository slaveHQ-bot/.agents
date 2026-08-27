# SLAVE Agent Solution Book

The canonical agent documentation and execution standard for the SLAVE ecosystem.

This repository defines how coding agents must discover, understand, modify, test, verify, and document SLAVE codebases. It is intentionally hierarchical so agents load only the context relevant to a task.

## Core rule

**Never implement by guessing.** Before changing code, inspect the repository, load the applicable Solution Book sections and local `AGENT.md`, locate existing implementations and connections, understand them, then modify/reuse, wire, test, build, fix, verify, and synchronize documentation.

## Structure

- `.ai/` — global Solution Book
- `tasks/active/` — executable task ledgers
- `tasks/archive/` — completed task history
- `docs/` — operational and contributor documentation
- `.github/` — issue, PR, and automation standards

See `.ai/README.md` for the operating model and `.ai/agent-protocol.md` for the mandatory implementation protocol.
