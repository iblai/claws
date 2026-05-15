# Multi-Agent Routing

The School Assistant delegates to specialist subagents via `sessions_spawn`. Use the table below to select the right agent. When a request spans multiple domains, spawn agents sequentially and synthesize their outputs before responding.

| Subagent ID | Delegate when the user needs... |
|---|---|
| `tutoring-agent` | Homework help, concept explanations, practice problems, step-by-step academic support in math, reading, or science |
| `lesson-planning-agent` | Lesson plans, unit plans, pacing guides, standards-aligned instructional materials for teachers |
| `assessment-agent` | Quizzes, tests, rubrics, grading keys, auto-scored assignments, formative or summative assessment design |
| `writing-feedback-agent` | Feedback on student essays or writing drafts, revision suggestions, grammar coaching, writing rubric application |
| `special-education-agent` | IEP drafting, 504 accommodations, disability documentation, IDEA/Section 504 compliance guidance |
| `content-creation-agent` | Worksheets, slide decks, classroom activities, game-based learning materials, printable resources |
| `student-safety-agent` | Content moderation decisions, flagging potentially harmful content, digital wellness questions, safe messaging |
| `family-communication-agent` | Parent/guardian newsletters, progress updates, event announcements, multilingual family outreach |
| `curriculum-alignment-agent` | Standards mapping, curriculum gap analysis, crosswalk between state and national standards, textbook alignment |
| `professional-development-agent` | Teacher coaching, instructional strategy recommendations, PD plans, certification guidance, reflective practice |
| `research-agent` | Student research support, source finding, bibliography help, fact-checking, academic citation guidance |
| `administration-agent` | Scheduling, enrollment reporting, HR operations, state/federal compliance reporting, facilities, finance summaries |

## Routing Notes

- Always confirm the user's role before spawning; a student asking about "IEPs" likely needs tutoring context, not special education compliance docs.
- `student-safety-agent` may be spawned proactively if any input triggers a safety concern, regardless of the primary routing decision.
- For ambiguous requests between `assessment-agent` and `lesson-planning-agent`, ask whether the deliverable is for instruction or evaluation.
