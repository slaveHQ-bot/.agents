# SLAVE API & Integration Contracts

This document defines boundaries, not guessed concrete method names. Exact signatures must be discovered in the target repository before implementation.

## Desktop ↔ Core

- Desktop UI is a client of the SLAVE application/core boundary.
- Commands and events must use the established IPC/RPC transport.
- UI must not import server-only internals simply to perform an operation.
- Errors must cross the boundary in a structured, user-safe form.

## Client ↔ Gateway

- Gateway is the controlled entry point for remote procedure/API operations within the application.
- Authentication and authorization occur at the established boundary.
- Request and response schemas must remain versionable.
- Breaking changes require explicit compatibility analysis.

## Agent Runtime ↔ Tools

- The agent runtime requests capabilities through the tool registry/execution abstraction.
- Tools return structured results and actionable errors.
- Tool execution must pass the applicable permission/safety policy.
- Tools must not silently mutate state outside their declared responsibility.

## Agent Runtime ↔ Models

- Runtime code should depend on model/provider abstractions rather than hard-coded provider implementations.
- BYOK credentials remain under the credential/secrets boundary.
- Model routing must support explicit user configuration and safe fallback behavior.

## Agent Runtime ↔ Memory

- Memory access goes through the memory/storage abstraction.
- Persistence format changes require migration planning.
- Retrieval must respect the current user's authorization and scope.

## Core ↔ Storage

- Database access belongs behind the established storage/state layer where one exists.
- Migrations are non-destructive unless explicitly authorized.
- Legacy compatibility must be considered before renaming or deleting persistent data.

## Optional remote services

Promotions, catalogs, update metadata, or other optional network services must not make the local application unusable when unavailable. Remote calls must have explicit timeout/error handling and offline-safe behavior.

## Contract change procedure

Before changing a contract:

1. Find the interface/type/schema.
2. Find every producer.
3. Find every consumer.
4. Find desktop/UI bindings.
5. Find tests and fixtures.
6. Determine compatibility impact.
7. Update the contract documentation.
8. Implement and verify all affected paths.
