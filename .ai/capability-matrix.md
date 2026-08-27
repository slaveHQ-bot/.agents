# SLAVE Capability Matrix

This is the target capability inventory. It is not evidence that a capability already exists. The implementation repository must record actual status.

| Capability | Specialist | Core dependencies | Verification |
|---|---|---|---|
| Chat | Master | session/model/runtime | E2E conversation |
| Planning | Master | model/memory | plan fixtures |
| Delegation | Master | agent registry/orchestrator | multi-agent E2E |
| Browser | Browser | browser adapter/CDP | browser E2E |
| Web research | Research | search/fetch/browser | evidence tests |
| Scraping | Scraper | browser/network/parser | extraction fixtures |
| Coding | Repo | filesystem/shell/git/model | repo E2E |
| Data | Data | files/database/runtime | dataset fixtures |
| Finance | Finance | data/docs/calculation | reconciliation fixtures |
| Images | Image | media runtime | asset validation |
| Video | Video | media/rendering | render smoke tests |
| Audio | Audio | media/audio runtime | output validation |
| Documents | Documents | file parsers/generators | format tests |
| Reports | Reports | research/data/docs/media | end-to-end report |
| QA | QA | test/build/runtime | regression suite |
| Desktop control | System | OS APIs/accessibility | sandboxed E2E |
| Filesystem | Tools | OS/filesystem | permission tests |
| Shell | Tools | process runtime | sandbox/security tests |
| MCP | Integrations | MCP adapter/permissions | protocol integration |
| Plugins | Integrations | registry/isolation | lifecycle tests |
| Scheduling | Automation | persistent scheduler | time-trigger tests |
| Notifications | Automation | channel adapters | delivery tests |
| Memory | Core | storage/retrieval | retrieval tests |
| Self-healing | Evaluator | diagnostics/retry | failure fixtures |
| Self-evaluation | Evaluator | benchmark harness | regression suite |
| Learning | Knowledge | memory/evaluation | controlled update tests |
| Self-adjusting | Orchestrator | evaluation signals | policy tests |
| Self-evolving | Master/Repo | task generation/code/test/review | approval-gated E2E |
| Cloud instances | Integrations | secure remote boundary | offline + remote tests |
| Mobile | Client | application boundary | client E2E |

## Status rule

Each real capability should eventually have an implementation status such as `planned`, `discovered`, `partial`, `wired`, `tested`, or `production-ready`, backed by repository evidence and task history.
