# SLAVE Cross-Domain Workflows

## Goal

SLAVE must compose browser, desktop, filesystem, coding, data, document, media and external-tool capabilities into one verified workflow.

## Execution graph

```text
User intent
  -> Master planning
  -> capability discovery
  -> specialist delegation
  -> tool/interface routing
  -> execution
  -> observation
  -> evaluation
  -> repair/re-plan if needed
  -> final artifact
  -> verification/report
```

## Example

A user can request a market research report. Master SLAVE may delegate research to Research SLAVE, extraction to Scraper SLAVE, processing to Data SLAVE, charts to Data/Creative capabilities, document assembly to Reports SLAVE, and QA to QA SLAVE. Browser, MCP/API, filesystem and desktop adapters can be mixed within the same graph.

## Completion rule

A workflow is not complete because an intermediate action succeeded. The expected final artifact/result must be validated against the original objective and all required constraints.

## Failure handling

Each node should expose structured success/failure information. Master SLAVE can retry, switch tools, delegate, or re-plan within configured limits. Irreversible or privileged operations require the appropriate user permission.
