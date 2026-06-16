# Writeback Packet

Use this packet when the Project Governor / Main Brain asks Codex or the user to
write durable updates into repository files.

## Coordination State

- Current coordination state: `<state before this writeback>`
- Requested next state: `<state after this writeback, or none>`
- Approval status: `<pending / approved>`
- Writeback type: `<NO_WRITEBACK, HANDOFF_UPDATE, MEMORY_UPDATE, DECISION_LOG_UPDATE, PROJECT_STATE_UPDATE, ROLE_UPDATE, CONTEXT_INDEX_UPDATE, ANTI_PATTERN_UPDATE, or USER_PREFERENCE_UPDATE>`

A user answering questions or saying "continue" is not approval to write durable
state. Approval must be explicit before this packet is executed.

## Target Files

- `<target file>`
- `<target file>`

User preference writebacks must follow `PREFERENCE_PROTOCOL.md`.

## Reason For Writeback

`<why this information needs to survive beyond the chat window>`

## Exact Update Scope

- `<section or entry to add/change>`
- `<section or entry to add/change>`

## Content To Add Or Change

```text
<proposed durable content>
```

## Forbidden Content

Do not include:

- secrets, tokens, API keys, passwords, or credentials;
- raw private chat transcripts;
- unnecessary personal information;
- unverified claims presented as truth;
- unrelated implementation details;
- content outside the target files.

## Validation

Run or perform:

- confirm the current coordination state allows this writeback;
- confirm explicit approval exists for the target files and content;
- confirm only target files changed;
- confirm no forbidden content was added;
- confirm the update matches the approved writeback type;
- confirm the affected governance links still point to existing files.

## Commit Rule

`<commit allowed or not allowed>`

If commit is allowed, include the requested commit message.
If commit is not allowed, leave changes unstaged and report `git status --short`.
