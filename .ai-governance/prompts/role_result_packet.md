# Role Result Packet

Return this packet from a specialist role window to the Project Governor / Main
Brain through the user.

## Role

`<role name>`

## Coordination State

- Current coordination state: `<state observed by this role>`
- Recommended next state: `<state recommended by this result, or none>`
- Approval status: `<not required / pending / approved>`
- Execution or writeback impact: `<none / durable writeback / Codex execution / role change>`

If this result recommends durable writeback, Codex execution, or role changes,
state whether user approval is required before the next step.

## Task Result

`<concise result of the assigned task>`

## Evidence

- `<file, user statement, command result, or other source>`
- `<file, user statement, command result, or other source>`

## Uncertainty

- `<unknown, stale input, missing evidence, or assumption risk>`

## Risks

- `<risk or tradeoff>`
- `<risk or tradeoff>`

## Recommended Writeback

`<NO_WRITEBACK, HANDOFF_UPDATE, MEMORY_UPDATE, DECISION_LOG_UPDATE, PROJECT_STATE_UPDATE, ROLE_UPDATE, CONTEXT_INDEX_UPDATE, ANTI_PATTERN_UPDATE, or USER_PREFERENCE_UPDATE>`

If a non-Project Governor / Main Brain role receives a user preference request,
recommend `USER_PREFERENCE_UPDATE` instead of persisting it directly.

## Files That Should Be Updated

- `<target governance file or none>`

## User Approval Needed

`<yes or no>`

Reason:

`<why approval is or is not needed>`

## Notes For Project Governor

- `<routing, follow-up, state transition, or review note>`
