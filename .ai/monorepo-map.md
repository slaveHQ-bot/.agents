# SLAVE Monorepo Map

## Purpose

A routing table for agents. It tells an agent where to investigate before editing code.

## Canonical SLAVE domains

| Domain | Start here | Then inspect |
|---|---|---|
| Desktop UI | desktop app entrypoint | chat, settings, account, task scheduling, IPC/RPC clients |
| Agent runtime | core agent runtime | sessions, prompts, tool execution, memory, routing |
| Gateway | gateway/RPC layer | authentication, session lifecycle, transport, API handlers |
| Authentication | local auth implementation | identity, credentials, provider credentials, authorization |
| Models | model provider/router layer | BYOK credentials, provider adapters, routing/fallback |
| Tools | tool registry/runtime | browser, desktop/system, files, shell, media and safety gates |
| Memory | memory host/store | persistence, retrieval, indexing, lifecycle |
| Storage | state/database layer | migrations, schemas, repositories, locking |
| Channels | channel adapters | inbound/outbound message lifecycle |
| Scheduling | scheduler/task engine | persistence, execution, retries, notifications |
| Plugins | plugin system | discovery, permissions, lifecycle and isolation |
| Telemetry | telemetry provider | local/offline defaults and explicit user configuration |
| Updates | update provider | local packaging and optional user-controlled update paths |

## Known SLAVE codebase baseline

The primary SLAVE core has historically been a pnpm monorepo with `src/` as the main application/core area and workspace packages around it. Desktop targets include Tauri/Linux and macOS/SwiftUI components.

**Important:** this map is a routing aid, not permission to assume paths. Before implementation, inspect the actual target repository and update this map if its structure differs.

## Existing SLAVE architectural areas

- CLI and application lifecycle
- Gateway/RPC server
- Agent runtime and sessions
- Tools
- Memory host
- Secrets and authentication
- Configuration
- Channels
- Plugins/providers
- Desktop shells
- Local SQLite/state persistence

## Search protocol

For any feature:

1. Search by user-facing feature name.
2. Search by domain concept.
3. Search for types/interfaces.
4. Search callers and consumers.
5. Search tests.
6. Search desktop/UI bindings.
7. Search gateway/API/IPC wiring.
8. Search configuration and persistence.
9. Only then choose the implementation point.

Never treat this document as proof that a file exists. The repository itself is authoritative for exact paths.
