# SLAVE Architecture

## Product model

SLAVE is designed as a local-first AI operating environment: the user owns the application, credentials, data, agents, automations and connections. The architecture should permit optional user-controlled cloud instances without making cloud infrastructure a mandatory dependency.

## Major layers

```text
Desktop / Mobile / CLI
        │
        ▼
Application Boundary (IPC / RPC / API)
        │
        ▼
Gateway / Application Services
        │
        ├── Authentication & Authorization
        ├── Agent Runtime
        │     ├── Model Router → Provider Adapters
        │     ├── Tool Registry → Tool Implementations
        │     └── Memory Host → Storage
        ├── Scheduler / Automations
        ├── Channels
        └── Plugins / Extensions
                │
                ▼
        Local State / Secrets / Filesystem
```

## Independence from OpenClaw

SLAVE originated from an OpenClaw codebase, but its target architecture is independent. OpenClaw-specific cloud authentication, remote session signing, telemetry, branding, and mandatory remote services must not become hidden runtime dependencies.

Compatibility/migration code may exist where required, but it must have a documented purpose and safe migration path.

## Authentication

SLAVE uses a local operator identity and local credential management model. Model/provider credentials are user-owned secrets and must remain behind the credential boundary.

## State

SQLite/local state is preferred for local persistence where appropriate. Database migrations must be explicit, backward-aware, and non-destructive by default.

## Desktop

Desktop applications are shells around the same application/core capabilities. A feature is not complete merely because its UI exists; its command/event path must reach the actual core implementation and return a verified result.

## Agent capability model

Specialized capabilities may include browser automation, computer/system control, research, creative/media work, data operations, personal assistance, advising, QA, sales and finance. These should remain composable through common agent/tool interfaces rather than creating isolated duplicate runtimes.

## Architecture change rule

When architecture changes, update the relevant `.ai/` document and local `AGENT.md` files in the same task/PR.
