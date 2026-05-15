# K-12 Segment Configuration

This directory contains a complete, drop-in NemoClaw/OpenClaw agent configuration for the K-12 education segment. It defines one parent "School Assistant" agent and twelve specialist subagents covering the full range of K-12 workflows from adaptive tutoring to district administration.

## Agent Roster

| Agent ID | Name | Role |
|---|---|---|
| `k-12-assistant` | School Assistant | Segment entry point; greets users, interprets intent, delegates to specialists |
| `tutoring-agent` | Tutor | Adaptive academic support in math, reading, and science |
| `lesson-planning-agent` | Lesson Planner | Standards-aligned lesson and unit plan creation |
| `assessment-agent` | Assessment Builder | Quiz generation, rubric creation, and auto-grading |
| `writing-feedback-agent` | Writing Coach | Student writing review and revision guidance |
| `special-education-agent` | Special Education Support | IEP, 504, and accommodation support |
| `content-creation-agent` | Content Creator | Worksheets, presentations, and classroom activities |
| `student-safety-agent` | Safety Monitor | Content moderation and student safety guardrails |
| `family-communication-agent` | Family Communicator | Parent updates, newsletters, and multilingual outreach |
| `curriculum-alignment-agent` | Curriculum Aligner | Standards mapping and curriculum gap analysis |
| `professional-development-agent` | PD Coach | Teacher professional development and coaching |
| `research-agent` | Research Guide | Student research support and citation guidance |
| `administration-agent` | School Administrator | Scheduling, reporting, and district operations |

The parent agent (`k-12-assistant`) is the default entry point. It accepts requests from teachers, students, families, and staff, then delegates to the appropriate specialist subagent via `sessions_spawn`.

## Directory Structure

```
k-12/
├── README.md               <- this file
├── openclaw.json           <- NemoClaw gateway configuration
├── .config-hash            <- sha256 of openclaw.json
├── .env.example            <- sample API credential variables (copy to ~/.openclaw/.env)
├── workspace/
│   └── .gitkeep            <- shared writable workspace (empty at deploy time)
├── skills/
│   └── <platform>/
│       └── SKILL.md        <- tool-skill definition for a third-party integration
└── agents/
    └── <agent-id>/
        └── agent/
            ├── auth-profiles.json
            ├── IDENTITY.md
            ├── SOUL.md
            ├── TOOLS.md
            ├── AGENTS.md        <- parent agent only
            ├── MEMORY.md        <- optional: seed long-term facts (regulation/standards-heavy agents)
            ├── HEARTBEAT.md     <- optional: periodic monitoring checklist (schedule-driven agents only)
            ├── BOOTSTRAP.md     <- optional: one-time first-run setup steps (consumed after first use)
            └── USER.md          <- optional: user/environment-specific context (rarely needed)
```

## Import Instructions

Follow these steps to import this configuration into a NemoClaw sandbox.

1. **Copy this directory into the sandbox.**
   Copy the entire contents of this directory into `/sandbox/.openclaw/` on the NemoClaw host. After copying, the path `/sandbox/.openclaw/openclaw.json` must exist.

   ```bash
   cp -r k-12/. /sandbox/.openclaw/
   ```

2. **Set ownership on the agents directory.**
   Ensure the `agents/` subdirectories and workspace are owned by the sandbox user (typically `sandbox`):

   ```bash
   chown -R sandbox:sandbox /sandbox/.openclaw/agents /sandbox/.openclaw/workspace
   ```

3. **Replace the sample API credentials.**
   Every agent directory contains `agent/auth-profiles.json` with placeholder values. Replace the `apiKey` value in each file with a real Anthropic API key before starting the gateway:

   ```bash
   # Example: update one agent
   nano /sandbox/.openclaw/agents/k-12-assistant/agent/auth-profiles.json
   ```

   The placeholder value is:
   `sk-ant-api03-SAMPLE-PLACEHOLDER-NOT-A-REAL-KEY-0000000000000000000000000000000000000000`

4. **Set up third-party platform credentials.**
   Copy `.env.example` to `~/.openclaw/.env` and replace every placeholder value with a real API key or OAuth credential for the platforms your deployment will use:

   ```bash
   cp /sandbox/.openclaw/.env.example ~/.openclaw/.env
   nano ~/.openclaw/.env
   ```

   `.env.example` is committed to the repository as a sample template representing the OpenClaw daemon env file `~/.openclaw/.env`; all its values are non-functional placeholders. The real `~/.openclaw/.env` should never be committed. See the [Tool Skills](#tool-skills) section for the full list of platforms and the variables each one requires.

5. **Recompute the configuration hash.**
   If you modify `openclaw.json` after copying, recompute the hash so the gateway accepts the configuration:

   ```bash
   cd /sandbox/.openclaw
   shasum -a 256 openclaw.json > .config-hash
   ```

   On Linux use `sha256sum` instead of `shasum -a 256`.

6. **Reload the OpenClaw gateway.**
   Restart or reload the OpenClaw service to pick up the new configuration:

   ```bash
   systemctl reload openclaw
   # or
   openclaw reload
   ```

The `k-12-assistant` agent is marked `"default": true` in `openclaw.json` and will be the agent that receives incoming sessions unless a specific agent ID is requested.

## Tool Skills

The `skills/` directory contains one subdirectory per third-party platform, each with a `SKILL.md` file. Each file describes the platform's API surface, the operations agents can perform, and the credential variables required. All skills draw credentials from `~/.openclaw/.env` on the OpenClaw daemon host — `.env.example` is the committed sample template with non-functional placeholder values that you copy and fill in during deployment (see step 4 of the import instructions above).

| Skill directory | Description |
|---|---|
| `canvas/` | Canvas LMS (Instructure) — read and write courses, modules, assignments, rubrics, grades, and submissions for K-12 classroom workflows. |
| `classdojo/` | ClassDojo — post classroom story updates and send direct messages to authorized guardians for K-12 family engagement and communication. |
| `ebsco/` | EBSCO school databases (EBSCOhost, Explora) — search peer-reviewed articles, reference materials, and grade-leveled nonfiction from school-licensed academic databases. |
| `edulastic/` | Edulastic — generate, import, and manage standards-aligned assessments; retrieve performance data and class mastery reports for K-12 assessment workflows. |
| `frontline/` | Frontline Education suite — access HR, absence management, professional development, and special education data across Frontline's K-12 platform products. |
| `google-classroom/` | Google Classroom — read and write courses, coursework, materials, and student submissions via the Google Classroom API for K-12 workflows. |
| `google-workspace-edu/` | Google Workspace for Education — read and write files in Google Drive, create and edit Docs and Slides, and manage folder structure for K-12 content workflows. |
| `iready/` | iReady (Curriculum Associates) — retrieve student diagnostic placement levels and domain scores to align tutoring and instructional content to each student's instructional zone. |
| `khan-academy/` | Khan Academy — retrieve student skill mastery, exercise progress, and course completion data to personalize tutoring and avoid re-teaching mastered content. |
| `nwea-map/` | NWEA MAP Growth — retrieve student RIT scores, instructional area recommendations, and growth projections to calibrate tutoring and instructional support. |
| `parentsquare/` | ParentSquare — compose, schedule, and send school-to-family communications (mass messages, direct messages, announcements) and read delivery analytics. |
| `powerschool/` | PowerSchool SIS — read and write student records, enrollment, attendance, grades, and demographic data for K-12 school and district operations. |

## Compliance Notes

- All agents follow FERPA and COPPA guidelines: student PII is never transmitted outside the sandbox.
- The `student-safety-agent` follows CIPA requirements for content filtering in school environments.
- The `special-education-agent` follows IDEA 2004 and Section 504 of the Rehabilitation Act.
- All sandbox processes run as the non-root `sandbox` user with seccomp and landlock enabled.
