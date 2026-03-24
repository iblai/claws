Parse $ARGUMENTS as `<vertical> <agent-name>`. The vertical is the first token (e.g., `higher-education`, `enterprise`, `k-12`, `small-business`, or a new vertical). The agent-name is the second token and must use kebab-case with an `-agent` suffix (e.g., `tutoring-agent`, `hr-support-agent`). If the arguments are missing or malformed, ask the user to provide them in the format `<vertical> <agent-name>`.

You are scaffolding a new agent for the iblai-claw-agents repository. Follow every step below carefully.

---

## Step 1: Understand the agent's domain

Before writing any files, research and reason about:

1. **What this agent does** -- based on the agent name and vertical, determine the agent's core purpose, who it serves, and what outcomes it delivers.
2. **Industry landscape** -- identify 5-10 real platforms, tools, and systems commonly used in this agent's domain (e.g., for an `hr-support-agent` in enterprise, that means Workday, BambooHR, ADP, etc.). These will populate DATA.md.
3. **Compliance requirements** -- determine which regulations apply to this vertical and agent role:
   - Higher education: FERPA, COPPA (if minors), Title IX, ADA, GLBA (financial)
   - K-12: FERPA, COPPA, CIPA, IDEA, state-specific student privacy laws
   - Enterprise: SOX, HIPAA (if health data), GDPR/CCPA (if PII), PCI DSS (if payments)
   - Small business: PCI DSS (if payments), state tax compliance, FLSA, ADA
   - Healthcare: HIPAA, HITECH, 42 CFR Part 2
   - Finance: SOX, GLBA, PCI DSS, BSA/AML, FINRA
   - Other verticals: identify the relevant regulations
4. **Competitor analysis** -- think about what a best-in-class AI assistant in this role would do well, what pitfalls to avoid, and what behavioral guidelines would make it trustworthy and effective.
5. **Network egress needs** -- determine what external systems the agent might need to reach (these become `<PLACEHOLDER_HOST>` entries in SECURITY.md).

---

## Step 2: Check for existing agents

Look at the existing agents in `agents/<vertical>/` to ensure this agent does not duplicate an existing one. If a very similar agent already exists, warn the user and ask whether to proceed or differentiate the new agent.

Also review 2-3 existing agents in the same vertical (or a neighboring vertical if this is a new one) to match the tone, depth, and formatting conventions already established.

---

## Step 3: Create the agent directory and required files

Create the directory at `agents/<vertical>/<agent-name>/` and write all six required files.

### IDENTITY.md

Exactly 3 lines, no headings, no blank lines between fields:

```
Name: <A friendly, memorable name -- 1-3 words, not the agent-name>
Role: <One sentence describing what the agent does>
Vibe: <Three adjectives, comma-separated>
```

The Name should be a human-friendly persona name (e.g., "Study Buddy", "Onboarding Guide", "Policy Navigator"), NOT the directory name.

### SOUL.md

Start with a single lead paragraph (one sentence) that captures the agent's core mission. Follow with 7-9 bullet points as behavioral guidelines. Each bullet should:
- Start with an action verb
- Be specific and actionable, not generic
- Reflect best practices from competitor analysis
- Include at least one bullet about knowing limits / escalation
- Include at least one bullet about honesty / transparency
- Never include bullets about "being helpful" -- that is assumed

Do NOT add a heading. The file starts directly with the lead paragraph.

### MODEL.md

A single line:

```
anthropic/claude-sonnet-4-5-20250929
```

### SECURITY.md

Follow this exact structure with proper YAML code blocks:

```markdown
# Security Configuration

NemoClaw sandbox policy for this agent.<compliance note if applicable>

## Network Policy

Deny-by-default egress. Only explicitly listed endpoints are reachable.

\```yaml
network:
  default: deny
  enforcement: strict
  tls: required
  rules:
    - name: inference
      endpoints:
        - "api.anthropic.com:443"
        - "statsig.anthropic.com:443"
        - "sentry.io:443"
      binaries:
        - "/usr/local/bin/claude"
      methods: ["*"]

    - name: openclaw
      endpoints:
        - "openclaw.ai:443"
        - "docs.openclaw.ai:443"
      binaries:
        - "/usr/local/bin/openclaw"
      methods: ["GET", "POST"]

    - name: clawhub
      endpoints:
        - "clawhub.com:443"
      binaries:
        - "/usr/local/bin/openclaw"
      methods: ["GET", "POST"]

    - name: <agent_specific_service>
      endpoints:
        - "<PLACEHOLDER_HOST>:443"
      binaries:
        - "/usr/local/bin/claude"
      methods: ["GET"] or ["GET", "POST"] as appropriate
\```

## Filesystem Policy

\```yaml
filesystem:
  rules:
    - path: /sandbox
      access: read-write
    - path: /tmp
      access: read-write
    - path: /sandbox/.openclaw-data
      access: read-write
    - path: /dev/null
      access: read-write
    - path: /sandbox/.openclaw
      access: read-only
    - path: /usr
      access: read-only
    - path: /lib
      access: read-only
    - path: /etc
      access: read-only
    - path: /proc
      access: read-only
    - path: /dev/urandom
      access: read-only
\```

## Process Isolation

\```yaml
process:
  run_as_user: sandbox
  run_as_group: sandbox
  seccomp: enabled
  landlock: enabled
\```

## Inference Routing

\```yaml
inference:
  route: local
  gateway: openshell
  credentials: host-only
  credential_store: ~/.nemoclaw/credentials.json
  credential_mode: "0600"
\```

## Supply Chain

\```yaml
supply_chain:
  blueprint_digest_verification: enabled
  docker_image_pinning: enabled
\```
```

Rules for SECURITY.md:
- The `inference`, `openclaw`, and `clawhub` rules are always included verbatim.
- Add 1-3 agent-specific network rules with `<PLACEHOLDER_HOST>` style endpoints (e.g., `<LMS_HOST>`, `<HRIS_HOST>`, `<ACCOUNTING_HOST>`). Name them descriptively (e.g., `lms_platform`, `hris_system`, `payment_processor`).
- If the vertical has compliance requirements (FERPA, HIPAA, etc.), add a note after the first line: e.g., `FERPA compliant -- no student PII leaves the sandbox.`
- The filesystem, process, inference, and supply chain sections are always identical across agents.

### TOOLS.md

A short description (1 line) followed by 3-5 bullet points listing available integrations. Each bullet should name a specific tool capability relevant to this agent's domain. Do NOT add a heading.

### DATA.md

This file must be comprehensive. Structure:

```markdown
# Data Sources

Systems and platforms commonly accessed for <agent purpose description>.

## <Category 1>

- **<Platform Name>** -- brief description
  - **<Entity/dataset>**: field1, field2, field3, field4, field5
  - **<Entity/dataset>**: field1, field2, field3, field4, field5

## <Category 2>
...
```

Rules for DATA.md:
- Include 4-7 categories relevant to the agent's domain
- Each category should have 2-5 real platform names (not made-up ones)
- Each platform should list 1-4 data entities/datasets with specific field names
- Use the double-dash ` -- ` separator after platform names (not colons)
- Fields should be realistic (snake_case), representing actual data the agent would consume
- Look at existing DATA.md files in the repo for calibration on depth and specificity

---

## Step 4: Determine if optional files are needed

Evaluate whether the agent needs any optional files. Only create them if there is a genuine reason:

- **CONFIG.json** -- Only if the agent needs non-default settings. Create if:
  - The agent is proactive/monitoring and needs a heartbeat schedule (e.g., `{"heartbeat": {"every": "1h"}}`)
  - The agent needs session-scoped isolation
  - Do NOT create CONFIG.json if there are no non-default settings

- **HEARTBEAT.md** -- Only if the agent proactively monitors something. Create as a checklist of periodic tasks using `- [ ]` format. Typical for: retention agents, compliance agents, safety agents, monitoring agents.

- **MEMORY.md** -- Only if the agent needs seed knowledge that does not belong in SOUL.md. Typical for: compliance agents (regulation summaries), financial agents (aid formulas), policy-heavy agents. Write as brief factual statements, not instructions.

- **BOOTSTRAP.md** -- Only if the agent needs one-time first-run setup steps. Typical for: onboarding agents, agents that need to verify integrations on first launch. Write as a numbered list of setup actions.

- **AGENTS.md** -- Only if this agent routes to other agents. Rarely needed.

- **USER.md** -- Only if the agent needs user-specific context. Rarely needed for templates.

If none of these are needed, do not create them.

---

## Step 5: Update README.md

After creating all files, update the README.md:

1. If this is a new vertical not already in the README, add a new section under `## Verticals` with a description and table.
2. If the vertical already exists, add a row to the existing vertical's table with the agent name and role.
3. Update the repository structure tree if needed to include the new agent directory.
4. Update the agent count in the vertical description if one is mentioned.

---

## Step 6: Verify

After creating all files, list the contents of the new agent directory to confirm all files were created. Read back IDENTITY.md and SOUL.md to verify formatting. Confirm:
- IDENTITY.md is exactly 3 lines with Name/Role/Vibe
- SOUL.md starts with a lead paragraph (no heading), followed by 7-9 bullets
- MODEL.md is exactly one line
- SECURITY.md has all 5 sections (Network, Filesystem, Process, Inference, Supply Chain)
- TOOLS.md has a description line and 3-5 bullets
- DATA.md has 4-7 categories with real platforms and specific fields
- No unnecessary optional files were created

Report what was created and whether any optional files were included (and why).
