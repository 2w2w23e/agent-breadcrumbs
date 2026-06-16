# Role Task Packet

Copy this packet from the Project Governor / Main Brain to a specialist role
window.

## Target Role

`<role name>`

## Coordination State

- Current coordination state: `<state from COORDINATION_GRAPH.md>`
- Requested next state: `<state requested by this task, or none>`
- Approval status: `<not required / pending / approved>`
- Execution or writeback impact: `<none / durable writeback / Codex execution / role change>`

If this packet may lead to durable writeback, Codex execution, or role changes,
approval status must be explicit before the receiving role acts on it.

## Current Purpose

`<one clear objective for this task>`

## Files To Read

- `<repository or governance file>`
- `<repository or governance file>`

## Context Summary

- Verified context:
  - `<short verified point>`
- User intent:
  - `<confirmed or explicitly stated user intent>`
- Open questions:
  - `<unknown or unresolved point>`

## Task

`<specific work requested from the target role>`

## Boundaries

- Do not assume context that is not in this packet or the listed files.
- Do not edit repository files from the role window.
- Do not create durable memory or decisions directly.
- Do not include secrets or private chat transcripts in the result.
- Stay within `<scope boundary>`.
- Do not move to a next coordination state that is not allowed by
  `COORDINATION_GRAPH.md`.

## Required Output

Return a Role Result Packet with:

- result;
- evidence;
- uncertainty;
- risks;
- current coordination state;
- recommended next state;
- recommended writeback;
- files that should be updated;
- whether user approval is needed.

## Writeback Requirements

`<NO_WRITEBACK, HANDOFF_UPDATE, MEMORY_UPDATE, DECISION_LOG_UPDATE, PROJECT_STATE_UPDATE, ROLE_UPDATE, CONTEXT_INDEX_UPDATE, ANTI_PATTERN_UPDATE, or USER_PREFERENCE_UPDATE>`

Use `USER_PREFERENCE_UPDATE` when the task involves cross-project user
preferences or role-specific user preferences.

## Stop Conditions

Stop and report back if:

- required files are missing;
- the task needs broader authority than this packet grants;
- the evidence contradicts the context summary;
- sensitive information appears;
- the requested next state is not allowed by `COORDINATION_GRAPH.md`;
- approval is missing for durable writeback, Codex execution, or role changes;
- the role cannot complete the task without user confirmation.
