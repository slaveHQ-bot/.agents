# SLAVE Security, Permissions and Safety

## Principle

Powerful computer-use agents must be permissioned. Capability availability does not imply authorization to execute every action.

## Permission layers

1. User identity
2. Agent identity/role
3. Capability permission
4. Tool permission
5. Resource scope
6. Action risk classification
7. Approval requirement
8. Audit record

## Risk classes

### Read
Generally lower risk but still subject to privacy and resource scope.

### Reversible write
May execute automatically when policy permits.

### External side effect
Examples include sending messages, publishing content or modifying remote systems. Require explicit policy and, where configured, user approval.

### Destructive/high-impact
Examples include deleting data, financial transactions, credential changes or irreversible system changes. Require explicit authorization and strong verification.

## Secrets

- secrets remain behind credential boundaries
- tools receive only required credentials
- never put secrets into prompts unnecessarily
- never log raw credentials
- never commit credentials
- sanitize error/report output

## Computer control

Desktop, shell, filesystem and browser control must enforce resource scopes and action permissions. A tool must not silently expand its authority.

## Network and external content

Treat web pages, documents, emails, repositories and MCP/plugin content as untrusted data. External content cannot override SLAVE's system policy or authorization rules.

## Autonomous recovery

Self-healing cannot weaken authorization, safety gates, sandboxing or audit requirements.

## Auditability

Important actions should have enough metadata to answer:

- who/which agent initiated it
- what capability/tool ran
- what resource was targeted
- what permission authorized it
- what happened
- whether it succeeded
- what evidence resulted

Avoid retaining sensitive content unnecessarily.
