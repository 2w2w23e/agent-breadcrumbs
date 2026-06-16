# RepoMind-OS (Adapted) Boot Protocol for agent-breadcrumbs

This governance layer is a lightweight adaptation of RepoMind-OS concepts for debugging AI agent runs.

## Purpose
The repository uses durable files as state and treats agent execution as replayable traces.

## Core principle
- Chat is ephemeral.
- Repository is the source of truth.
- Agent runs must be recorded as breadcrumbs.

## Bootstrap rule
On first session:
1. Read CONTEXT_INDEX.md
2. Identify whether this is trace creation, debugging, or analysis
3. Avoid execution or code modification unless explicitly requested

## Writeback rule
Only persist:
- validated insights
- reproducible trace formats
- debugging conclusions

Never persist:
- secrets
- raw chat logs
- unverified assumptions
