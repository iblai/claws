<div align="center">

<a href="https://ibl.ai"><img src="https://ibl.ai/images/iblai-logo.png" alt="ibl.ai" width="300"></a>

# Claw Agents

48 pre-built agent configurations for [OpenClaw](https://github.com/iblai/iblai-claw-setup) instances, organized by vertical. Each agent is a workspace-ready set of configuration files that can be pushed to a claw instance via the [ibl.ai platform API](https://github.com/iblai/iblai-claw-setup/blob/main/docs/platform-integration.md).

[![OpenClaw](https://img.shields.io/badge/OpenClaw-292929?logoColor=white)](https://github.com/iblai/iblai-claw-setup)
[![NemoClaw](https://img.shields.io/badge/NemoClaw-76B900?logo=nvidia&logoColor=white)](https://github.com/NVIDIA/NemoClaw)
[![ibl.ai Platform](https://img.shields.io/badge/ibl.ai_Platform-4A90D9?logoColor=white)](https://ibl.ai)
[![License: Proprietary](https://img.shields.io/badge/License-Proprietary-blue.svg)](#license)

</div>

---

## Agent Configuration

Each agent directory contains workspace files that map to the [agent configuration API](https://github.com/iblai/iblai-claw-setup/blob/main/docs/platform-integration.md#configure-the-agent):

| File | API Field | Pushed As | Description |
|------|-----------|-----------|-------------|
| `IDENTITY.md` | `identity` | IDENTITY.md | Agent persona -- name, role, vibe |
| `SOUL.md` | `soul` | SOUL.md | Behavioral guidelines -- personality, values, boundaries |
| `MODEL.md` | `model` | config.patch | LLM model identifier |
| `CONFIG.json` | `config` | config.patch | Instance settings (heartbeat schedule, session isolation) |
| `USER.md` | `user_context` | USER.md | User-specific environment details |
| `TOOLS.md` | `tools` | TOOLS.md | Environment-specific reference notes for tool usage |
| `AGENTS.md` | `agents` | AGENTS.md | Multi-agent routing configuration |
| `BOOTSTRAP.md` | `bootstrap` | BOOTSTRAP.md | One-time first-run instructions (consumed after use) |
| `HEARTBEAT.md` | `heartbeat` | HEARTBEAT.md | Periodic awareness checklist content |
| `MEMORY.md` | `memory` | MEMORY.md | Seed memory -- long-term curated facts |
| `SECURITY.md` | -- | -- | [NemoClaw](https://github.com/NVIDIA/NemoClaw) sandbox security policy |

All text fields are optional. Each agent has its own directory with one file per configuration option. `SECURITY.md` defines the [NemoClaw](https://github.com/NVIDIA/NemoClaw) sandbox policy (network egress, filesystem, process isolation, inference routing).

## Repository Structure

```
agents/
├── higher-education/           # University and college agents (12)
│   ├── enrollment-agent/
│   ├── application-reader-agent/
│   ├── financial-aid-agent/
│   ├── academic-advisor-agent/
│   ├── tutoring-agent/
│   ├── retention-agent/
│   ├── student-services-agent/
│   ├── career-services-agent/
│   ├── faculty-agent/
│   ├── research-agent/
│   ├── alumni-agent/
│   └── it-help-desk-agent/
├── enterprise/                 # Corporate and business agents (16)
│   ├── personal-learning-agent/
│   ├── onboarding-agent/
│   ├── career-development-agent/
│   ├── training-creation-agent/
│   ├── knowledge-management-agent/
│   ├── hr-support-agent/
│   ├── it-help-desk-agent/
│   ├── compliance-agent/
│   ├── sales-enablement-agent/
│   ├── operations-agent/
│   ├── knowledge-agent/
│   ├── customer-support-agent/
│   ├── meeting-agent/
│   ├── marketing-agent/
│   ├── engineering-agent/
│   └── data-analysis-agent/
├── k-12/                       # K-12 education agents (12)
│   ├── tutoring-agent/
│   ├── lesson-planning-agent/
│   ├── assessment-agent/
│   ├── writing-feedback-agent/
│   ├── special-education-agent/
│   ├── content-creation-agent/
│   ├── student-safety-agent/
│   ├── family-communication-agent/
│   ├── curriculum-alignment-agent/
│   ├── professional-development-agent/
│   ├── research-agent/
│   └── administration-agent/
└── small-business/             # Small business agents (8)
    ├── customer-support-agent/
    ├── sales-agent/
    ├── bookkeeping-agent/
    ├── social-media-agent/
    ├── scheduling-agent/
    ├── hiring-agent/
    ├── inventory-agent/
    └── website-agent/
```

## Usage

### Push an agent to your claw instance

1. Choose an agent from `agents/<vertical>/<agent-name>/`
2. Use the file contents as field values in the agent configuration API:

```bash
AGENT_DIR="agents/higher-education/tutoring-agent"

# Read each config file
IDENTITY=$(cat "$AGENT_DIR/IDENTITY.md")
SOUL=$(cat "$AGENT_DIR/SOUL.md")
TOOLS=$(cat "$AGENT_DIR/TOOLS.md")
MODEL=$(cat "$AGENT_DIR/MODEL.md")
CONFIG=$(cat "$AGENT_DIR/CONFIG.json" 2>/dev/null || echo '{}')

# Push to your agent config
curl -X PATCH "https://platform.ibl.ai/api/ai-mentor/orgs/$ORG/agent-configs/$AGENT_ID/" \
  -H "Content-Type: application/json" \
  -H "Authorization: Token $API_TOKEN" \
  -d "$(jq -n \
    --arg identity "$IDENTITY" \
    --arg soul "$SOUL" \
    --arg tools "$TOOLS" \
    --arg model "$MODEL" \
    --argjson config "$CONFIG" \
    '{identity: $identity, soul: $soul, tools: $tools, model: $model, config: $config}'
  )"
```

3. Push the configuration to the instance:

```bash
curl -X POST "https://platform.ibl.ai/api/ai-mentor/orgs/$ORG/claw/mentor-configs/$MENTOR_CONFIG_ID/push-config/" \
  -H "Authorization: Token $API_TOKEN"
```

### Adding a new agent

1. Create a directory under the appropriate vertical: `agents/<vertical>/<agent-name>/`
2. Add at minimum `IDENTITY.md`, `SOUL.md`, and `MODEL.md`
3. Add `SECURITY.md` with a [NemoClaw](https://github.com/NVIDIA/NemoClaw) sandbox policy
4. Add optional workspace files (`TOOLS.md`, `MEMORY.md`, `HEARTBEAT.md`, etc.) as needed
5. Add `CONFIG.json` only if the agent needs non-default instance settings

## Verticals

### Higher Education

12 agents covering the complete student lifecycle -- from enrollment through alumni engagement. Designed for universities and colleges.

| Agent | Role |
|-------|------|
| Enrollment Agent | Recruitment campaigns and admissions inquiries |
| Application Reader Agent | Application scoring and transcript evaluation |
| Financial Aid Agent | FAFSA support, aid eligibility, scholarship matching |
| Academic Advisor Agent | Degree planning, course registration, graduation requirements |
| Tutoring Agent | Personalized 1-on-1 academic support across subjects |
| Retention Agent | At-risk student identification and early intervention |
| Student Services Agent | Housing, campus life, and wellness support |
| Career Services Agent | Resume building, interview prep, job search |
| Faculty Agent | Syllabus creation, grading, course material development |
| Research Agent | Literature review, citation management, grant writing |
| Alumni Agent | Alumni engagement, fundraising, event coordination |
| IT Help Desk Agent | Technical support for campus systems |

### Enterprise

16 agents spanning employee development, manager productivity, and workforce operations. Built for corporate learning and operational support.

| Agent | Role |
|-------|------|
| Personal Learning Agent | Skill development, certification prep, learning paths |
| Onboarding Agent | New hire orientation, policy guidance, system access |
| Career Development Agent | Internal mobility, skill gap analysis, promotion readiness |
| Training Creation Agent | Course development, assessment generation, compliance modules |
| Knowledge Management Agent | Knowledge capture, process documentation, preservation |
| HR Support Agent | Policy Q&A, performance reviews, leave management |
| IT Help Desk Agent | Technical support, password resets, troubleshooting |
| Compliance Agent | Regulatory training, certification tracking, audit prep |
| Sales Enablement Agent | Product knowledge, competitive intelligence, pitch prep |
| Operations Agent | SOP guidance, safety protocols, quality standards |
| Knowledge Agent | Enterprise search and institutional knowledge access |
| Customer Support Agent | Ticket resolution, customer inquiries, follow-ups |
| Meeting Agent | Meeting recaps, action items, follow-up tracking |
| Marketing Agent | Content creation, campaign planning, SEO |
| Engineering Agent | Code review, documentation, project onboarding |
| Data Analysis Agent | Reports, trend analysis, data-driven insights |

### K-12

12 agents supporting students, teachers, and administrators across the K-12 spectrum. Designed for school districts and education organizations with FERPA and COPPA compliance.

| Agent | Role |
|-------|------|
| Tutoring Agent | Adaptive homework help and academic support |
| Lesson Planning Agent | Standards-aligned lesson and unit plan creation |
| Assessment Agent | Quiz generation, rubric creation, and auto-grading |
| Writing Feedback Agent | Student writing review and developmental feedback |
| Special Education Agent | IEP, 504, and accommodation planning support |
| Content Creation Agent | Worksheets, presentations, and classroom activities |
| Student Safety Agent | Content moderation, safety guardrails, and digital wellness |
| Family Communication Agent | Parent updates, newsletters, and multilingual communication |
| Curriculum Alignment Agent | Standards mapping, vertical alignment, and curriculum compliance |
| Professional Development Agent | Teacher training, instructional coaching, and professional growth |
| Research Agent | Age-appropriate research support and source evaluation |
| Administration Agent | Scheduling, reporting, and district operations support |

### Small Business

8 agents covering core small business operations -- from customer acquisition through financial management. Built for lean teams that need to do more with less.

| Agent | Role |
|-------|------|
| Customer Support Agent | Customer inquiry handling, review management, service recovery |
| Sales Agent | Lead follow-up, proposal generation, pipeline management |
| Bookkeeping Agent | Invoicing, expense tracking, financial reporting, tax prep |
| Social Media Agent | Content creation, scheduling, community management |
| Scheduling Agent | Appointment booking, calendar management, reminders |
| Hiring Agent | Job posting, resume screening, interview scheduling |
| Inventory Agent | Stock tracking, reordering, supplier coordination |
| Website Agent | Website content updates, SEO optimization, analytics |

## License

Proprietary -- ibl.ai
