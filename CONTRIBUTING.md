# Contributing to the SLAVE Agent Standard

## Documentation-first development

Changes to this repository must improve the reliability of agents working on SLAVE.

### Before changing a rule

- identify the problem the rule solves
- check for an existing rule that covers it
- avoid contradictory guidance
- keep global rules in `.ai/`
- keep package-specific rules in local `AGENT.md`

### New task

Use `.ai/templates/task-spec-template.md`. Tasks must be deterministic and verifiable.

### New repository structure

Update `.ai/monorepo-map.md` and relevant architecture/contracts documentation.

### PR requirement

Use `.ai/templates/pull-request-template.md` and include actual verification evidence.
