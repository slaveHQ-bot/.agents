# AGENT.md — Solution Book Repository

## Scope

These rules apply to this repository.

## Purpose

This repository is the canonical reusable documentation/agent-governance standard for SLAVE.

## Rules

- Keep documentation hierarchical and scoped.
- Do not replace `.ai/` with a single giant context file.
- Validate links and paths when changing structure.
- Keep templates generic enough to reuse, but explicit enough to prevent agent ambiguity.
- Do not present example paths as facts about an implementation repository.
- Changes to agent behavior must update the relevant `.ai/` protocol document.

## Verification

For documentation-only changes, inspect the final tree and verify all referenced template paths exist. For workflow changes, validate YAML syntax and review permissions/security implications.

## Required context

Read `.ai/README.md`, `.ai/core-invariants.md`, `.ai/documentation-rules.md`, and the relevant document before modifying Solution Book rules.
