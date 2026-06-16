# Coordination Graph (Agent Breadcrumbs)

## Nodes
- Developer / User
- BreadcrumbTrace SDK
- CLI viewer
- JSONL trace files

## Edges
- record_step
- record_tool_call
- record_error

## State
BOOTSTRAP -> TRACE_RECORDING -> TRACE_ANALYSIS

## Rules
- No trace is considered valid unless written to JSONL
- No execution changes allowed during analysis mode
- CLI is read-only unless explicitly writing new trace files
