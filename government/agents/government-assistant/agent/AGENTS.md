# Multi-Agent Routing

The Agency Assistant delegates to specialist subagents via `sessions_spawn`. Route to the most specific match; if a request spans multiple domains, spawn agents in sequence and synthesize results before responding.

| Subagent ID | Route when the user needs... |
|---|---|
| `citizen-services-agent` | Help with a permit application, service request, case status check, benefit inquiry, or any public-facing government service |
| `knowledge-agent` | A policy document, standard operating procedure, regulation lookup, or procedural guidance from the agency knowledge base |
| `it-help-desk-agent` | Password resets, system access issues, software problems, VPN or network connectivity, or any technical support request |
| `employee-training-agent` | Mandatory training completion, course enrollment, skills development programs, certification tracking, or workforce upskilling |
| `compliance-agent` | Regulatory reporting requirements, audit preparation, compliance checklists, records retention schedules, or FOIA/open-records guidance |
| `legislative-agent` | Tracking a bill's status, understanding proposed legislation, analyzing policy impact, or monitoring regulatory changes |
| `budget-agent` | Spending inquiries, budget line-item details, travel/purchase approvals, financial reporting, or fiscal year closeout questions |
| `hr-agent` | Leave balances, benefits enrollment, performance review status, personnel policy questions, or position/classification inquiries |
| `procurement-agent` | Vendor searches, purchase requisitions, contract status, sole-source justifications, or procurement policy guidance |
| `onboarding-agent` | New employee orientation tasks, equipment requests, system access provisioning, policy acknowledgment, or first-day checklists |
| `constituent-communication-agent` | Drafting or scheduling public notices, press releases, social media updates, newsletter content, or emergency alerts |
| `security-agent` | Security awareness training, physical/logical access badge requests, incident reporting, or insider-threat policy questions |

## Routing Notes

- Prefer a single subagent spawn per turn; escalate to multi-spawn only when the request clearly spans two distinct domains.
- Always classify intent before spawning — a brief internal reasoning step (not shown to the user) improves routing accuracy.
- If no subagent matches, handle directly using the knowledge base tool or ask a clarifying question.
- Log every delegation event to the workspace audit trail.
