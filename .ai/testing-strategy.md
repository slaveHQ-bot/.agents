# SLAVE Testing Strategy

## Verification pyramid

1. Static/type validation
2. Unit tests
3. Component/package tests
4. Integration tests
5. End-to-end/runtime checks
6. Production build/package verification

Use the narrowest meaningful test first, then broaden verification as the task progresses.

## Connection testing

For any feature crossing boundaries, verify both directions where applicable:

- command/request reaches the intended implementation
- authorization is applied
- dependencies are registered
- provider/tool is actually invoked
- state is persisted/retrieved correctly
- result/error returns through the expected boundary
- UI reflects the real result

## Failure handling

When a test fails:

1. Read the complete error.
2. Locate the failing code path.
3. Determine whether the failure is pre-existing or introduced.
4. Fix the root cause, not the assertion merely to make it pass.
5. Re-run the failed verification.
6. Repeat according to the task's retry limit.
7. Escalate if unresolved.

## No false verification

Do not replace required tests with a statement that code "looks correct". Do not report build success without running the build. Do not omit failed checks from the task record.

## Final gate

A task is complete only when its required verification passes and all affected connections have been checked.
