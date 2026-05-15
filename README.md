<div align="center">

<a href="https://ibl.ai"><img src="https://ibl.ai/images/iblai-logo.png" alt="ibl.ai" width="300"></a>

# Claw Agents

Drop-in [OpenClaw](https://github.com/iblai/iblai-claw-setup) / [NemoClaw](https://github.com/NVIDIA/NemoClaw) agent configurations for every [ibl.ai](https://ibl.ai) solution segment. Each segment is a complete multi-agent system — one parent orchestrator plus a roster of specialist subagents — packaged so a NemoClaw host can import it with zero conversion.

[![OpenClaw](https://img.shields.io/badge/OpenClaw-292929?logoColor=white)](https://github.com/iblai/iblai-claw-setup)
[![NemoClaw](https://img.shields.io/badge/NemoClaw-76B900?logo=nvidia&logoColor=white)](https://github.com/NVIDIA/NemoClaw)
[![ibl.ai Platform](https://img.shields.io/badge/ibl.ai_Platform-4A90D9?logoColor=white)](https://ibl.ai)
[![License: Proprietary](https://img.shields.io/badge/License-Proprietary-blue.svg)](#license)

</div>

---

## Overview

This repository contains **7 segment configurations**, one for each segment in the ibl.ai Solutions menu. Every segment directory is a self-contained OpenClaw gateway config: copy its contents into `/sandbox/.openclaw/` on a NemoClaw host, recompute one hash, and reload the gateway.

| Segment | Parent agent | Subagents | Tool skills |
|---------|--------------|-----------|-------------|
| [`higher-education/`](higher-education/) | Campus Assistant | 16 | 10 |
| [`k-12/`](k-12/) | School Assistant | 12 | 12 |
| [`enterprise/`](enterprise/) | Workplace Assistant | 12 | 12 |
| [`government/`](government/) | Agency Assistant | 12 | 10 |
| [`legal/`](legal/) | Firm Assistant | 12 | 11 |
| [`financial-services/`](financial-services/) | Advisory Assistant | 12 | 11 |
| [`medical-healthcare/`](medical-healthcare/) | Care Assistant | 12 | 10 |

**95 agents** (7 parents + 88 specialists) and **76 tool skills** in total. This is a configuration-only repository — no application code, build system, or tests.

## How a segment is structured

Each segment has one **parent agent** (the default entry point) and a set of **specialist subagents**. The parent interprets each request and delegates to the right specialist via the `sessions_spawn` tool; the subagents it may spawn are listed in its `subagents.allowAgents`. The parent then synthesizes the results.

```
<segment>/
├── README.md                  # segment overview + import steps
├── openclaw.json              # gateway config — every agent, model, sandbox, skills
├── .config-hash               # sha256 of openclaw.json
├── .env.example               # template for ~/.openclaw/.env (sample credentials)
├── workspace/
│   └── .gitkeep               # shared writable workspace (empty at install)
├── skills/
│   └── <tool>/
│       └── SKILL.md           # one skill directory per major third-party tool
└── agents/
    └── <agent-id>/
        └── agent/
            ├── IDENTITY.md          # persona — name, role, vibe
            ├── SOUL.md              # behavioral guidelines
            ├── TOOLS.md             # tool/integration notes + data sources
            ├── AGENTS.md            # multi-agent routing table (parent only)
            ├── USER.md              # user/environment context    (optional)
            ├── BOOTSTRAP.md         # one-time first-run setup     (optional)
            ├── HEARTBEAT.md         # periodic awareness checklist (optional)
            ├── MEMORY.md            # seed long-term facts         (optional)
            └── auth-profiles.json   # per-agent provider credentials (sample)
```

### Runtime-only by design

The repo contains **only what the OpenClaw/NemoClaw runtime actually loads** — the per-agent files above plus `openclaw.json`, `.config-hash`, `skills/`, and `.env.example`. Model, instance config, sandbox/security policy, and skill wiring all live in `openclaw.json`; there is no `MODEL.md`, `CONFIG.json`, `SECURITY.md`, or `DATA.md`, because the runtime never read them. Optional files (`USER.md`, `BOOTSTRAP.md`, `HEARTBEAT.md`, `MEMORY.md`) appear only on agents that genuinely need them.

### `openclaw.json`

The OpenClaw gateway configuration. Every agent — parent and subagents — is declared in `agents.list[]`. The parent carries `default: true` and a `subagents.allowAgents` list naming every child. `agents.defaults` holds the shared `model`, `subagents` limits, the `skills` array, and the `sandbox` block (the runtime's security policy). Each agent entry points at its workspace via `agentDir`, and carries its `model` and any `heartbeat`/`session` settings. After any edit to `openclaw.json`, recompute `.config-hash`.

### Skills & credentials

`skills/` holds one skill **directory** per major platform popular in the segment (Canvas, Banner, Salesforce, ServiceNow, Epic FHIR, Westlaw, and so on) — each a `<tool>/SKILL.md` with `name`, `description`, and a single-line `metadata` declaring the env vars it needs. `agents.defaults.skills` in `openclaw.json` wires them to the agents by name. Skill credentials resolve from environment variables; `.env.example` is the committed template for the OpenClaw daemon env file `~/.openclaw/.env`.

Both `auth-profiles.json` (per-agent LLM provider keys) and `.env.example` (per-tool API credentials) ship with **clearly-marked, non-functional sample placeholders**. Replace them with real values before deploying.

## Importing a segment to NemoClaw

```bash
# 1. Copy the segment into the sandbox config root
cp -r higher-education/. /sandbox/.openclaw/

# 2. Give the sandbox user ownership of the agent workspaces
chown -R sandbox:sandbox /sandbox/.openclaw/agents/

# 3. Fill in real credentials
cp /sandbox/.openclaw/.env.example ~/.openclaw/.env
#    edit ~/.openclaw/.env and each agents/*/agent/auth-profiles.json

# 4. Recompute the config hash
cd /sandbox/.openclaw && sha256sum openclaw.json > .config-hash

# 5. Reload the gateway
openclaw reload
```

Each segment's own `README.md` carries the full step-by-step.

## Agent rosters

<details>
<summary><strong>Higher Education</strong> — Campus Assistant + 16 specialists</summary>

Enrollment · Application Reader · Financial Aid · Academic Advisor · Tutoring · Retention · Student Services · Career Services · Faculty · Research · Alumni · IT Help Desk · Prospective Student · Yield · Continuing Education · Administrative
</details>

<details>
<summary><strong>K-12</strong> — School Assistant + 12 specialists</summary>

Tutoring · Lesson Planning · Assessment · Writing Feedback · Special Education · Content Creation · Student Safety · Family Communication · Curriculum Alignment · Professional Development · Research · Administration
</details>

<details>
<summary><strong>Enterprise</strong> — Workplace Assistant + 12 specialists</summary>

Knowledge · IT Help Desk · Sales Enablement · Customer Support · Onboarding · HR · Marketing · Engineering · Meeting · Training · Data Analysis · Operations
</details>

<details>
<summary><strong>Government</strong> — Agency Assistant + 12 specialists</summary>

Citizen Services · Knowledge · IT Help Desk · Employee Training · Compliance · Legislative · Budget · HR · Procurement · Onboarding · Constituent Communication · Security
</details>

<details>
<summary><strong>Legal</strong> — Firm Assistant + 12 specialists</summary>

Case Research · Contract Review · Client Intake · Billing & Time · Discovery · Compliance · Knowledge · Brief Drafting · Conflicts Check · Training · Docket Management · IT Help Desk
</details>

<details>
<summary><strong>Financial Services</strong> — Advisory Assistant + 12 specialists</summary>

Compliance · Risk Assessment · Client Advisory · Regulatory Reporting · Portfolio Analysis · Employee Training · KYC/AML · Fraud Detection · Client Onboarding · Knowledge · IT Help Desk · Operations
</details>

<details>
<summary><strong>Medical / Healthcare</strong> — Care Assistant + 12 specialists</summary>

Clinical Support · Patient Education · Medical Coding · Compliance Training · Research · Provider Onboarding · Prior Authorization · Care Coordination · Documentation · Quality Improvement · IT Help Desk · Knowledge Management
</details>

## Adding an agent to a segment

1. Create `<segment>/agents/<agent-name>-agent/agent/` with `IDENTITY.md`, `SOUL.md`, `TOOLS.md`, and `auth-profiles.json` (add `USER.md`/`BOOTSTRAP.md`/`HEARTBEAT.md`/`MEMORY.md` only if warranted).
2. Add an entry to `agents.list[]` in `<segment>/openclaw.json` (set `id`, `name`, `agentDir`, `model`, `identity`, `tools`).
3. Add the new id to the parent agent's `subagents.allowAgents` and to its `AGENTS.md` routing table.
4. Recompute the hash: `sha256sum openclaw.json > .config-hash`.
5. Update the segment `README.md` and the roster in this file.

## Adding a new segment

Mirror an existing segment directory: a parent agent plus specialist subagents, an `openclaw.json` declaring them all, a `skills/` directory of `<tool>/SKILL.md` directories, `.env.example`, a `README.md`, and a recomputed `.config-hash`.

## License

Proprietary — ibl.ai
