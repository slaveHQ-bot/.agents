# SLAVE Integration Strategy

## Principle

External systems are adapters into SLAVE's common capability and permission model. Do not create a separate execution path for every integration.

## Integration classes

### Browser

Support browser automation through an adapter layer. Where available, CDP and other compatible automation protocols may be exposed as tools behind the browser capability boundary.

### MCP

MCP servers, tools, resources and prompts should be discovered through a controlled registry. Each integration declares capabilities, permissions, health and lifecycle. Local and user-authorized remote servers may be supported.

### Desktop / OS

OS-specific implementations sit behind a system-control abstraction. Examples include Linux, macOS and future Windows adapters. Do not put OS-specific operations into the agent planner.

### Cloud

Cloud connections are optional. A connection profile defines endpoint, authentication, capabilities, permissions and data-transfer policy. Local operation must remain functional without it unless a feature explicitly requires the remote resource.

### Plugins

Plugins are extensions, not privileged bypasses. They require declared capabilities, version compatibility, lifecycle handling and permission checks.

## Connection lifecycle

```text
DISCOVER → VALIDATE → AUTHORIZE → CONNECT → HEALTHY
                                      ↓
                                  DEGRADED
                                      ↓
                                  RECOVER
                                      ↓
                                 DISCONNECT
```

## Integration contract

Every integration should provide, conceptually:

- identity
- capabilities
- version/protocol
- configuration schema
- credential requirements
- permissions
- health check
- connect/disconnect
- invoke/read/write operations as applicable
- structured errors
- timeout/cancellation
- audit events

## Secrets

Credentials are stored only through the established secrets/credential boundary. Agents and logs must not receive secrets unnecessarily.

## Offline behavior

Optional integrations must fail gracefully. Cached/local functionality should remain available where possible.

## Testing

Every integration requires at least:

- adapter contract tests
- permission tests
- error/timeout tests
- registration/discovery tests
- real integration tests where feasible
- end-to-end verification for user-visible flows
