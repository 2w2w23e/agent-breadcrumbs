# agent-breadcrumbs

Replayable breadcrumbs for debugging AI agent runs.

`agent-breadcrumbs` is a small Python toolkit for recording an AI agent run as a durable, replayable trace. It is designed for agent developers who want to debug decisions, tool calls, inputs, outputs, errors, recovery attempts, and handoffs without relying on a lost chat window or scattered logs.

## Why this exists

Modern agent debugging usually fails in one of three ways:

1. the chat window remembers context but the repository does not;
2. the logs record low-level events but not intent or recovery decisions;
3. Codex or another coding agent edits files without a reusable task boundary.

This project treats each agent run as a breadcrumb trail: small structured events that can be replayed, summarized, reviewed, and attached to future work.

## RepoMind-OS integration

This repository includes a lightweight governance layer adapted from `2w2w23e/RepoMind-OS`.

The integration keeps these RepoMind ideas:

- repository files are durable project state;
- GPT or Codex windows are temporary workbenches;
- context should be routed through a small context index instead of rereading everything;
- important decisions and handoffs should be written back deliberately;
- Codex tasks should include allowed files, forbidden files, validation commands, and stop conditions.

For this repository, the governance layer is focused on agent trace tooling instead of general project governance. Start from `.ai-governance/BOOT.md` when opening a fresh GPT or Codex session for this repo.

## Current status

Pre-alpha scaffold. The repository now contains:

- `.ai-governance/` project governance files;
- `AGENTS.md` for repository-level AI/Codex instructions;
- a minimal Python package under `src/agent_breadcrumbs/`;
- a CLI entrypoint named `agent-breadcrumbs`;
- a basic example and unit test.

## Quick start

```bash
python -m venv .venv
source .venv/bin/activate
pip install -e .
python examples/basic_trace.py
agent-breadcrumbs view trace.jsonl
```

## Minimal Python usage

```python
from agent_breadcrumbs import BreadcrumbTrace

trace = BreadcrumbTrace(run_id="demo")
trace.record_step("plan", "Decide what files to inspect first")
trace.record_tool_call("fetch_file", {"path": "README.md"}, {"ok": True})
trace.record_error("validation", "Example failure", recoverable=True)
trace.write_jsonl("trace.jsonl")
```

## Trace format

Each breadcrumb is one JSON object per line:

```json
{"run_id":"demo","event_type":"step","name":"plan","summary":"Decide what files to inspect first","payload":{},"ts":"2026-06-16T00:00:00Z"}
```

The format is intentionally simple so traces can be reviewed in GitHub, attached to issues, or consumed by another viewer later.

## Safety notes

Do not write secrets, tokens, credentials, raw private chat transcripts, or unnecessary personal information into traces or governance files.

## License

License is not selected yet. Add a license before advertising public reuse.