# TASK-[ID]: [Short imperative title]

## 1. Objective

[Exact outcome required.]

## 2. Context Loading (Agent Instructions)

Before writing code, MUST read:

- `.ai/README.md`
- relevant `.ai/monorepo-map.md` sections
- relevant `.ai/core-invariants.md` sections
- relevant `.ai/api-contracts.md` sections
- `[path]/AGENT.md`
- `[existing implementation files]`
- `[relevant tests]`

## 3. Current-State Findings

Record the existing implementation, owners, data flow, dependencies, and known gaps discovered during reconnaissance.

## 4. Boundaries & Invariants

- [Must not change]
- [Compatibility requirement]
- [Security/safety requirement]

## 5. Execution Plan

Execute sequentially. Do not proceed until verification passes.

- [ ] **Step 1: [name].** [Change].
  - **Verification:** `[command]`
  - **Expected:** [result]

- [ ] **Step 2: [name].** [Change].
  - **Verification:** `[command]`
  - **Expected:** [result]

## 6. Integration/Wiring Verification

- [ ] Registration/discovery verified
- [ ] Boundary/IPC/RPC/API path verified
- [ ] Authorization/permissions verified
- [ ] Persistence/configuration verified
- [ ] UI/result path verified
- [ ] Error/fallback path verified

## 7. Final Verification

- [ ] Targeted tests
- [ ] Integration tests
- [ ] Typecheck/lint as applicable
- [ ] Production build
- [ ] Final connection audit
- [ ] Solution Book synchronized
- [ ] Local `AGENT.md` synchronized where needed

## 8. Completion Evidence

Document actual commands, outcomes, changed files, and known limitations. Never fabricate verification.
