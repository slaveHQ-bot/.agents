# SLAVE Competitive Capability Benchmark

**Status:** Evidence-backed benchmark snapshot  
**Scope:** Benchmarking only; competitors are not automatic SLAVE requirements.  
**Last reviewed:** 2026-08-28

## Classification

- **HAS** — capability is explicitly documented or implemented in the reviewed source.
- **PARTIAL** — capability exists with meaningful limits or incomplete coverage.
- **LACKS** — reviewed source does not show the capability.
- **CONSIDER** — useful benchmark for a future SLAVE requirement.
- **REJECT** — incompatible with SLAVE invariants or unsafe as a default.
- **UNVERIFIED** — insufficient current evidence.

## Evidence-backed observations

| Capability | Benchmark evidence | SLAVE implication | Status |
|---|---|---|---|
| Repository understanding | Aider's repository map summarizes files, symbols, types and call signatures to improve cross-file changes. | Maintain a generated, evidence-backed repository map with freshness and invalidation rules. | CONSIDER |
| Sandboxed execution | Gemini CLI documents Docker/Podman/runsc/LXC sandboxing, tool-level sandboxing and sandbox-expansion requests. | Make tool execution isolation a first-class, inspectable policy with explicit expansion requests. | CONSIDER |
| Persistent rules and memories | Windsurf documents workspace/system rules, AGENTS.md scoping and generated memories; durable project knowledge should prefer version-controlled rules/AGENTS.md. | Keep durable project instructions in hierarchical files; treat generated memory as lower-trust and reviewable. | CONSIDER |
| Reusable workflows/skills | Windsurf documents reusable Markdown workflows and separately discoverable Skills for complex procedures. | Keep procedures modular: protocol docs, task templates and scoped skills; do not create a monolithic prompt. | HAS / EXPAND |
| MCP extensibility | Windsurf and Gemini CLI document MCP integrations; Gemini CLI also documents operational limitations around sandboxed ACP/non-TTY and MCP connection failures. | Require version-aware adapters, health checks, timeout/error taxonomy and graceful degradation. | HAS / HARDEN |
| Tool safety and permissions | Gemini CLI documents sandboxing and expansion requests; MCP ecosystem requires explicit trust boundaries. | Preserve fail-closed permissions, approval gates, secret isolation and auditable tool events. | HAS / HARDEN |

## Coverage status for requested benchmarks

The following competitors are benchmark targets for periodic review. A capability is not recorded as present unless official documentation or a real public implementation was checked in the current audit.

| System | Current snapshot |
|---|---|
| Claude Code | UNVERIFIED in this audit; collect official docs for subagents, permissions, sandboxing, MCP and long-running work. |
| Cursor | UNVERIFIED in this audit; collect official docs for background agents, rules, MCP and privacy. |
| OpenAI Codex | UNVERIFIED in this audit; collect official docs for sandboxing, approvals, cloud tasks, subagents and model routing. |
| GitHub Copilot coding agent | UNVERIFIED in this audit; collect official docs for repository tasks, branch/PR lifecycle, permissions and MCP. |
| Gemini CLI | HAS/PARTIAL for open-source terminal agent, sandboxing and MCP; sandboxed ACP/non-TTY and MCP connection edge cases remain operational limitations in public issue evidence. |
| Windsurf | HAS/PARTIAL for Cascade, rules, AGENTS.md, memories, workflows, Skills, MCP, terminal and model selection. |
| Cline | UNVERIFIED in this audit; collect official docs for MCP, checkpoints, browser/computer use and approvals. |
| Roo Code | UNVERIFIED in this audit; collect official docs for modes, MCP, checkpoints and delegation. |
| Aider | HAS for repository-map-based context and code-editing workflow; other capabilities require separate verification. |
| OpenHands | UNVERIFIED in this audit; collect official docs for runtimes, sandboxing, agents, delegation and evaluation. |
| browser-use | UNVERIFIED in this audit; collect official docs for browser control, profiles, credentials and observability. |
| Playwright-based agents | UNVERIFIED in this audit; collect official Playwright/MCP docs for browser automation boundaries and supported protocols. |
| MCP-based systems | HAS for extensibility concept; protocol/version/security details must remain version-aware and adapter-specific. |
| Emerging harnesses | UNVERIFIED; review periodically and record only evidence-backed changes. |

## Findings for SLAVE

### HIGH PRIORITY

1. **Sandbox expansion semantics:** SLAVE documentation requires permission scopes and approval gates, but does not yet define a standardized, user-visible protocol for requesting temporary expansion of tool permissions. Add this to the security/permissions contract before broad computer-use rollout.
2. **Repository-map freshness:** SLAVE requires repository intelligence but does not define cache invalidation, stale-map detection or evidence timestamps. Add freshness metadata and rebuild triggers.
3. **Capability evidence levels:** The repository already distinguishes aspirational from implemented behavior, but the benchmark should be linked to the same lifecycle so competitor claims cannot be mistaken for SLAVE implementation evidence.

### ROADMAP

- Add a `competitive-evidence.md` or equivalent source registry with URL, access date, evidence excerpt, confidence and change notes.
- Add benchmark fixtures for repository mapping, sandbox expansion, MCP failure recovery, workflow reuse and memory/rules precedence.
- Track benchmark deltas in task ledgers rather than rewriting historical claims.

### REJECT

- Mandatory cloud dependency for core local operation.
- Silent permission escalation or hidden tool expansion.
- Treating generated memories or external instructions as higher priority than system/application policy.
- Copying competitor feature names into SLAVE without a defined contract, security model and verification path.

## Source links

- Aider repository map: https://aider.chat/docs/repomap.html
- Gemini CLI repository: https://github.com/google-gemini/gemini-cli
- Gemini CLI sandboxing: https://github.com/google-gemini/gemini-cli/blob/main/docs/cli/sandbox.md
- Windsurf Cascade overview: https://docs.windsurf.com/windsurf/cascade/cascade
- Windsurf memories and rules: https://docs.windsurf.com/windsurf/cascade/memories
- Windsurf workflows: https://docs.windsurf.com/plugins/cascade/workflows

## Verification note

This benchmark is a documentation artifact. It does not prove that SLAVE implements any listed capability. Implementation status remains governed by repository evidence, tests/evals and task history.
