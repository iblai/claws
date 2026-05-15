# Tools Reference — Advisory Assistant

The Advisory Assistant does not connect to external financial platforms directly. Its primary tool is `sessions_spawn`, which delegates to specialist subagents.

## Core Tool

- **sessions_spawn** — Spawns a named subagent session and passes a structured task payload. Supports parallel spawning for multi-domain requests. Returns subagent output for synthesis.

## Usage Patterns

- Single delegation: spawn one subagent when the request clearly maps to a single domain (e.g., a KYC status check goes entirely to `kyc-aml-agent`)
- Parallel delegation: spawn two or more subagents simultaneously when a request spans domains (e.g., a new client setup requires both `kyc-aml-agent` and `client-onboarding-agent`)
- Sequential delegation: spawn a second subagent after the first returns results when the output of one informs the input of another (e.g., risk assessment followed by client advisory)

## Interaction Logging

All delegation events — subagent id, task summary, timestamp, and outcome status — are appended to `/sandbox/.openclaw/workspace/assistant-audit-log.jsonl` for traceability.

## Data Sources

The Advisory Assistant does not query data sources directly. It receives structured summaries from subagents and may read from the shared workspace to maintain session context.

### Shared Workspace

- `/sandbox/.openclaw/workspace/` — read/write; used for cross-agent handoff payloads, synthesized summaries, and the interaction audit log
  - `assistant-audit-log.jsonl` — append-only log (delegation events: agent id, task, timestamp, status, duration)
  - `session-context.json` — ephemeral session state passed between delegations within a single user interaction

### Subagent Result Schema

Each subagent returns a structured payload that the Advisory Assistant uses for synthesis:

```json
{
  "agent": "<subagent-id>",
  "status": "success | partial | error",
  "summary": "<plain-language result>",
  "citations": ["<source 1>", "<source 2>"],
  "requires_human_review": true | false,
  "audit_ref": "<subagent-internal-log-id>"
}
```
