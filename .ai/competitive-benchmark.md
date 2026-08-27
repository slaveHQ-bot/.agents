# SLAVE Competitive Harness Benchmark

**Audit date:** 2026-08-27  
**Scope:** capability benchmarking only; competitor behavior is not implementation evidence for SLAVE.  
**Decision labels:** `HAS`, `PARTIAL`, `LACKS`, `CONSIDER`, `REJECT`, `UNVERIFIED`.

## Benchmark principles

- Competitors are benchmarks, not automatic SLAVE requirements.
- Prefer official technical documentation and real public implementations.
- A capability is not adopted merely because a competitor exposes it; SLAVE must preserve local-first, BYOK, explicit permissions, evidence-based completion and distributed documentation.
- Current SLAVE status remains `UNVERIFIED` for capabilities that require implementation evidence outside this documentation repository.
- Refresh this document when a competitor or protocol materially changes a benchmarked capability.

## Current benchmark

| System | Coding / repo | Planning / agents | Long-running / parallel | Browser / computer | MCP / extensibility | Safety / sandbox / approvals | Memory / recovery / observability | SLAVE classification |
|---|---|---|---|---|---|---|---|---|
| Claude Code | Strong terminal/file/repo agent | Strong subagents/agent-team patterns | Strong | Via integrations/tools; browser capability often external | Strong MCP/hooks/skills | Strong permission modes; sandboxing depends on setup | Strong session/resume; extensible hooks | `CONSIDER` for workflow patterns; verify current product details before adoption |
| Cursor | Strong IDE/repo understanding and terminal | Strong agent planning | **HAS** background agents and API | Via MCP/browser integrations | **HAS** MCP and extensions | Strong controls; background agents run remotely with internet | Strong background-agent status/follow-up | `CONSIDER` background execution patterns; reject cloud dependency as SLAVE default |
| OpenAI Codex | Strong coding/repo/tool execution | **HAS** subagents and multi-agent orchestration | **HAS** parallel subagents; configurable limits | **HAS/PARTIAL** computer-use/tool ecosystem depending on environment | **HAS** MCP/skills | Strong sandbox/approval model | **HAS** multi-agent visibility and workflow controls | `CONSIDER` orchestration, subagent roles and sandbox inheritance |
| GitHub Copilot coding agents | Strong repository/PR workflow | **HAS** agent + plan modes | **HAS** cloud-agent asynchronous workflow | MCP integrations; computer/browser depends on enabled tools | **HAS** MCP | Strong repo-scoped cloud permissions and firewall controls | **HAS** PR/CI/security integration | `CONSIDER` repository governance; `REJECT` GitHub-cloud dependency for local-first core |
| Gemini CLI | Strong CLI/repo/tool use | **HAS** plan mode and subagents | **HAS/PARTIAL** subagents/headless automation | **PARTIAL** through extensions/MCP | **HAS** MCP/extensions/hooks | **HAS** Docker/tool sandbox + explicit sandbox expansion | **HAS** checkpoint/restore; model routing | `CONSIDER` checkpointing and sandbox-expansion UX |
| Windsurf / Cascade | Strong IDE agent | **HAS/PARTIAL** workflows and agent modes | **PARTIAL**; background/developer-agent features are evolving | MCP/browser integrations | **HAS** MCP/workflows | **PARTIAL**; tool approval/auto-run and enterprise controls | **HAS/PARTIAL** memories, rules, checkpoints | `CONSIDER` reusable workflows and project rules |
| Cline | Strong local coding agent | **HAS** plan mode; task history | **HAS/PARTIAL** scheduling/hub/task automation in current CLI | Browser/computer through tools/MCP | **HAS** MCP/plugins | **HAS/PARTIAL** auto-approval and tool controls | **HAS** task history/diagnostics | `CONSIDER` local automation and explicit provider/model controls |
| Roo Code | Strong coding agent | **HAS** Architect/Debug/Ask/Code modes | **HAS** Orchestrator/boomerang delegation | Via tools/MCP | **HAS** MCP/custom modes | **HAS** per-mode tool access and approvals | **HAS/PARTIAL** mode persistence and task orchestration | `CONSIDER` role-based modes and delegated workflows |
| Aider | Strong Git/repo map/edit loop | **HAS** Architect mode | `PARTIAL` relative to full agent harnesses | `LACKS` as a core product capability | `PARTIAL` compared with MCP-native harnesses | Git-based edit/review safeguards; fewer general sandbox controls | **HAS/PARTIAL** chat history/repo map | `CONSIDER` repo-map + architect/editor separation; avoid copying its narrower runtime model |
| OpenHands | Strong coding agent/runtime | **HAS** agent SDK and composable workflows | **HAS** remote/managed execution patterns | **HAS** browser in sandbox | **HAS** MCP, ACP, model routing | **HAS** Docker/remote sandbox providers | **HAS** tracing, conversation control, context condenser | `CONSIDER` sandbox/runtime abstraction and ACP interoperability |
| browser-use | `PARTIAL` coding; browser-first | **HAS** natural-language browser agent | **HAS** persistent sessions/scheduling/cloud tasks | **HAS** browser automation | Integrates with agent tools/CLI | Cloud-managed security controls; local mode also exists | **HAS** profiles, persistent login state, recordings | `CONSIDER` browser session/profile architecture; `REJECT` cloud-only assumptions |
| Playwright MCP | `LACKS` as a general coding agent; specialized browser substrate | `PARTIAL` as an agent tool | **HAS/PARTIAL** persistent browser sessions and multi-client attachment | **HAS** structured accessibility-based browser control | **HAS** native MCP | Capability/tool exposure can be constrained; authorization is delegated to host client | **HAS/PARTIAL** tracing, storage, recording and attachable sessions | `CONSIDER` as browser adapter baseline |
| MCP ecosystem | Not a coding agent | Not an orchestrator by itself | **HAS/PARTIAL** protocol Tasks/extensions enable richer workflows | Tool/server dependent | **HAS** protocol-native tools/resources/prompts/extensions | **HAS/PARTIAL** evolving authorization and security model | **HAS/PARTIAL** request/task semantics depend on implementation | `HAS` as integration boundary; track protocol versions rather than freezing one revision |

## Capability-gap conclusions for SLAVE

### IMMEDIATE / HIGH PRIORITY

1. **Explicit capability status ledger:** the current capability matrix lists targets but does not carry evidence-backed status per capability. Add status/evidence fields when permitted implementation evidence is available.
2. **Subagent contract maturity:** benchmark leaders now expose concrete subagent roles, parallel execution, limits and inheritance of permissions/sandbox policy. SLAVE's conceptual contract should remain abstract but the governance layer should specify required evidence for spawning, cancellation, result collection and failure propagation.
3. **Checkpoint / rollback semantics:** Gemini CLI and other harnesses make rollback a first-class agent operation. SLAVE should treat checkpoint, rollback and recovery evidence as a capability concern, not merely a test detail.
4. **Sandbox expansion and approval semantics:** permission requests need explicit resource scope, reason, approval result and audit evidence. This strengthens the existing SLAVE permission layers.
5. **Browser substrate:** Playwright MCP demonstrates structured accessibility snapshots, persistent sessions and capability-scoped tools. Browser SLAVE should benchmark these adapter-level primitives rather than inventing a proprietary browser protocol.
6. **Observability:** benchmark systems increasingly expose live agent state, traces, session history and background-task status. SLAVE orchestration should require durable execution identity and inspectable state transitions.

### ROADMAP / CONSIDER

- Background/long-running execution with pause, resume, cancel, retry budget and durable status.
- Explicit subagent budgets: max depth, concurrency, token/time/tool budgets and resource scopes.
- Role-scoped model selection and routing.
- Reusable workflow/skill packages with provenance and versioning.
- Local checkpointing before high-impact file changes.
- Standard browser adapter based on accessibility-first interaction plus optional vision/CDP/network capabilities.
- ACP/MCP interoperability where it preserves SLAVE policy and audit boundaries.
- Programmatic/batched tool execution for bounded, deterministic processing stages.

### REJECT / EXCLUDED

- Making cloud execution mandatory because competitors use hosted agents.
- Treating competitor proprietary behavior as an architectural dependency.
- Copying remote browser infrastructure as the default SLAVE browser model.
- Removing approval/sandbox controls to match faster autonomous modes.
- Replacing the distributed Solution Book with a monolithic agent-context file.

## Primary evidence sources

- Claude Code CLI: https://docs.anthropic.com/en/docs/claude-code/cli-usage
- Cursor Background Agents: https://docs.cursor.com/background-agent
- Cursor MCP: https://docs.cursor.com/context/model-context-protocol
- OpenAI Codex subagents: https://developers.openai.com/codex/subagents
- OpenAI Codex CLI: https://developers.openai.com/codex/cli
- GitHub Copilot agents: https://docs.github.com/en/copilot/responsible-use/agents
- GitHub Copilot agent mode + MCP: https://docs.github.com/en/copilot/tutorials/enhance-agent-mode-with-mcp
- Gemini CLI: https://geminicli.com/docs/
- Gemini sandbox: https://geminicli.com/docs/cli/sandbox/
- Gemini checkpointing: https://geminicli.com/docs/cli/checkpointing/
- Windsurf Cascade: https://docs.windsurf.com/windsurf/cascade/cascade
- Windsurf workflows: https://docs.windsurf.com/windsurf/cascade/workflows
- Cline CLI: https://docs.cline.bot/usage/cli-overview
- Cline MCP: https://docs.cline.bot/mcp/mcp-overview
- Roo Code modes: https://github.com/RooCodeInc/Roo-Code/blob/main/apps/docs/docs/basic-usage/using-modes.md
- Aider options: https://aider.chat/docs/config/options.html
- Aider modes: https://aider.chat/docs/usage/modes.html
- OpenHands SDK docs: https://docs.openhands.dev/llms.txt
- OpenHands sandbox: https://docs.openhands.dev/openhands/usage/sandboxes/overview
- Browser Use agent: https://docs.browser-use.com/cloud/agent/quickstart
- Browser Use CLI: https://docs.browser-use.com/open-source/browser-use-cli
- Playwright MCP: https://playwright.dev/mcp/introduction
- Playwright MCP capabilities: https://playwright.dev/mcp/capabilities
- MCP 2026-07-28 specification release: https://blog.modelcontextprotocol.io/posts/2026-07-28/
- OpenAI Symphony orchestration spec: https://openai.com/index/open-source-codex-orchestration-symphony/

## Verification state

This benchmark verifies public documentation and public implementation evidence for competitor capabilities only. It does **not** verify any SLAVE runtime capability. SLAVE capability status remains `UNVERIFIED` until evidence is available within the explicitly permitted implementation scope.
