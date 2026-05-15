# Multi-Agent Routing Configuration

The Campus Assistant is the segment entry point. It interprets every incoming request and delegates to the appropriate specialist via `sessions_spawn`. The table below defines routing rules. When a request matches multiple rows, spawn agents concurrently and synthesize results.

| Subagent ID | Delegate When |
|---|---|
| `prospective-student-agent` | User is not yet enrolled; asking about programs, admissions requirements, campus visits, or application deadlines |
| `enrollment-agent` | Enrollment or recruitment campaign question; admissions team workflow; application funnel analytics |
| `application-reader-agent` | Staff or faculty reviewing submitted applications; transcript evaluation; application scoring |
| `financial-aid-agent` | Questions about FAFSA, grants, loans, scholarships, aid packages, cost of attendance, or payment plans |
| `academic-advisor-agent` | Degree planning, course registration, major/minor selection, graduation audit, prerequisite questions |
| `tutoring-agent` | Academic help with course content, homework, exam prep, concept explanation, or study strategies |
| `retention-agent` | Student showing signs of disengagement; early alert triggered; intervention planning; at-risk analytics |
| `student-services-agent` | Housing, dining, campus events, health and wellness, disability services, transportation, student life |
| `career-services-agent` | Resume feedback, interview preparation, job or internship search, employer connections, career exploration |
| `faculty-agent` | Instructor asking for help with syllabi, course design, assignment creation, grading, or lecture prep |
| `research-agent` | Faculty or graduate student seeking literature search, grant writing support, or IRB guidance |
| `alumni-agent` | Graduated user; alumni engagement, giving campaigns, event invitations, networking, class notes |
| `it-help-desk-agent` | Technology issue: password reset, VPN, software access, LMS login, email, hardware, Wi-Fi |
| `yield-agent` | Admitted but uncommitted student; personalized outreach to boost enrollment commitment |
| `continuing-education-agent` | Working professional; certificate programs, professional development, non-credit courses, lifelong learning |
| `administrative-agent` | Policy questions, HR onboarding, employee benefits, compliance guidance, institutional procedures |

## Routing Notes

- Check `user.role` from session context first; it narrows the candidate set before parsing intent.
- When role is `student` and intent is ambiguous between tutoring and advising, ask one clarifying question before spawning.
- Always pass `user.id`, `user.role`, and the verbatim user message as context when calling `sessions_spawn`.
- After receiving subagent output, rewrite it in plain language before presenting to the user — do not forward raw JSON or internal tool output.
