# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

A library of pre-built agent configurations for OpenClaw instances, organized by vertical (higher-education, enterprise, k-12, small-business). This is a configuration-only repository -- no application code, no build system, no tests.

## Structure

Each agent lives at `agents/<vertical>/<agent-name>/` and contains workspace files that map to the [claw agent configuration API](https://github.com/iblai/iblai-claw-setup/blob/main/docs/platform-integration.md#configure-the-agent):

- `IDENTITY.md` -- agent persona (name, role, vibe)
- `SOUL.md` -- behavioral guidelines (personality, values, boundaries)
- `MODEL.md` -- LLM model identifier (one line, e.g. `anthropic/claude-sonnet-4-5-20250929`)
- `SECURITY.md` -- NemoClaw sandbox security policy (network, filesystem, process, inference)
- `TOOLS.md` -- environment-specific reference notes for tool usage
- `DATA.md` -- data sources with platform names and expected data fields per source, organized by category
- `CONFIG.json` -- instance settings (only when non-default, e.g. session scope, heartbeat schedule)
- Optional: `USER.md`, `AGENTS.md`, `BOOTSTRAP.md`, `HEARTBEAT.md`, `MEMORY.md`

## Conventions

- Agent directories use kebab-case with `-agent` suffix: `tutoring-agent`, `hr-support-agent`
- IDENTITY.md uses `Name:`, `Role:`, `Vibe:` fields
- SOUL.md contains behavioral guidelines as a lead paragraph followed by bullet points
- MODEL.md contains a single line with the model identifier; all agents default to `anthropic/claude-sonnet-4-5-20250929`
- SECURITY.md follows NemoClaw conventions: deny-by-default network egress, read-only system paths, non-root process isolation, credential-isolated inference routing
- CONFIG.json is only present when the agent needs non-default instance settings (session scope, heartbeat schedule)
- Only add optional workspace files (MEMORY.md, HEARTBEAT.md, BOOTSTRAP.md, etc.) when the agent genuinely needs them

## Adding a New Agent

1. Create `agents/<vertical>/<agent-name>/`
2. Write `IDENTITY.md` with Name, Role, and Vibe
3. Write `SOUL.md` with behavioral guidelines
4. Write `MODEL.md` with the model identifier
5. Write `SECURITY.md` with NemoClaw sandbox policy (use an existing agent's SECURITY.md as a template, customize network rules)
6. Write `TOOLS.md` with available integrations for the agent's domain
7. Write `DATA.md` with industry-common platforms and the specific data fields/entities expected from each
8. Optionally add `CONFIG.json`, `MEMORY.md`, `HEARTBEAT.md`, `BOOTSTRAP.md` as needed
9. Update the vertical table in README.md

## Slash Commands

- `/create-agent <vertical> <agent-name>` -- scaffolds a complete agent directory with all required files, researching industry platforms, data sources, and compliance requirements
