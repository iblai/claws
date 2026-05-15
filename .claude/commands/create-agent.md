Parse $ARGUMENTS as `<segment> <agent-name>`. The segment is the first token and must be one of: `higher-education`, `k-12`, `enterprise`, `government`, `legal`, `financial-services`, `medical-healthcare`. The agent-name is the second token, in kebab-case with an `-agent` suffix (e.g. `tutoring-agent`, `prior-authorization-agent`). If the arguments are missing or malformed, ask the user to provide them in the format `<segment> <agent-name>`.

You are scaffolding a new specialist subagent inside an existing segment. Each `<segment>/` directory is a drop-in OpenClaw/NemoClaw gateway config containing **only what the runtime reads**: one parent agent plus specialist subagents. Follow every step.

---

## Step 1: Understand the agent's domain

Before writing files, research and reason about:

1. **Purpose** -- the agent's core function, who it serves, what outcomes it delivers.
2. **Industry platforms** -- 5-10 real platforms, tools, and systems used in this domain. These populate `TOOLS.md`.
3. **Compliance** -- the regulations that apply (FERPA/COPPA/CIPA/IDEA; HIPAA/HITECH; SEC/FINRA/SOX/GLBA/BSA-AML; ABA ethics rules; Privacy Act/FOIA/FISMA/FAR; SOX/GDPR/CCPA).
4. **Behavior** -- what a best-in-class assistant in this role does well, and what guardrails make it trustworthy.

## Step 2: Check for duplicates and study the segment

Review `<segment>/agents/` to confirm the new agent does not duplicate an existing one. If a close match exists, warn the user and ask whether to proceed. Read 2-3 existing agents in the segment to match their tone, depth, and formatting — they are your templates.

## Step 3: Create the agent workspace

Create `<segment>/agents/<agent-name>/agent/` and write these files (the runtime reads only these):

- **`IDENTITY.md`** -- exactly 3 lines, no headings:
  ```
  Name: <friendly persona name, 1-3 words, not the directory name>
  Role: <one sentence describing what the agent does>
  Vibe: <three comma-separated adjectives>
  ```
- **`SOUL.md`** -- one lead paragraph (the agent's core mission), then 7-9 behavioral bullets. Each starts with an action verb and is specific. Include at least one bullet on knowing limits / escalation and one on honesty / transparency. No heading.
- **`TOOLS.md`** -- a short description, 3-5 bullets naming specific tool capabilities for this domain, then a `## Data Sources` section listing real platforms with their data entities and specific snake_case field names. Match the depth of existing `TOOLS.md` files in the segment.
- **`auth-profiles.json`** -- copy from an existing agent in the segment (sample placeholder LLM provider credentials, clearly marked non-functional).

Optional files — add ONLY if the agent genuinely needs them (they default to empty, so absence is valid):

- **`HEARTBEAT.md`** -- for agents that proactively monitor on a schedule. A one-line intro + a `- [ ]` checklist of periodic awareness tasks.
- **`MEMORY.md`** -- for rules/regulation-heavy agents. `# Seed Memory` heading + brief factual statements.
- **`BOOTSTRAP.md`** -- for agents with one-time first-run setup. `# Bootstrap` heading + numbered setup actions.
- **`USER.md`** -- only if the agent needs fixed user/environment context. Usually skip.

Do NOT create `MODEL.md`, `SECURITY.md`, `DATA.md`, or `CONFIG.json` — the runtime does not read them. Model, sandbox policy, and instance config all live in `openclaw.json`.

## Step 4: Register the agent in `openclaw.json`

Add an entry to `agents.list[]` in `<segment>/openclaw.json`, mirroring an existing subagent object:

```json
{
  "id": "<agent-name>",
  "name": "<persona name from IDENTITY.md>",
  "workspace": "/sandbox/.openclaw/workspace",
  "agentDir": "/sandbox/.openclaw/agents/<agent-name>/agent",
  "model": "anthropic/claude-sonnet-4-5-20250929",
  "identity": { "name": "<persona name>", "emoji": "<fitting emoji>" },
  "tools": { "profile": "full" }
}
```

Then add `<agent-name>` to the parent agent's `subagents.allowAgents` array. If the agent has a `HEARTBEAT.md`, also add a `"heartbeat": { "every": "<interval>" }` key to its entry. Never set the blocked config paths `gateway.auth`, `gateway.controlUi.dangerouslyDisableDeviceAuth`, `tools.exec.host`, `sandbox.mode`, `hooks.allowUnsafeExternalContent`.

## Step 5: Update the parent's `AGENTS.md`

Add a routing entry to `<segment>/agents/<segment>-assistant/agent/AGENTS.md` mapping the new agent id to the conditions under which the parent should delegate to it.

## Step 6: Recompute the config hash

From inside `<segment>/`, run: `shasum -a 256 openclaw.json > .config-hash`

## Step 7: Update documentation

- Add the new agent to the roster table/list in `<segment>/README.md`.
- Add it to the segment's roster in the root `README.md`, and bump the subagent count in the overview table.

## Step 8: Verify

Confirm:
- `IDENTITY.md` is 3 lines; `SOUL.md` is a lead paragraph + 7-9 bullets; `TOOLS.md` has a `## Data Sources` section; any optional files added are warranted.
- `openclaw.json` is still valid JSON, the new agent is in `agents.list[]`, and its id is in the parent's `subagents.allowAgents`.
- `.config-hash` matches the current `openclaw.json`.
- Both READMEs reflect the new agent.

Report what was created and confirm the hash was recomputed.
