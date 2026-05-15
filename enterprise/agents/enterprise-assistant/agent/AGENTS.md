# Agent Routing Configuration

The Workplace Assistant delegates to specialist subagents via `sessions_spawn`. Interpret employee intent and route to the most specific agent. When a request spans multiple domains, spawn agents in parallel and synthesize their outputs.

| Subagent ID | Delegate when the employee asks about... |
|---|---|
| `knowledge-agent` | Internal documentation, policies, procedures, company knowledge base search, institutional FAQs |
| `it-help-desk-agent` | Password resets, software access, hardware issues, VPN, account lockouts, ticket status |
| `sales-enablement-agent` | Competitive intelligence, deal strategy, prospect research, outreach templates, pricing guidance |
| `customer-support-agent` | Customer ticket resolution, account issues, refunds, escalations, follow-up communications |
| `onboarding-agent` | New hire orientation, first-day logistics, system access setup, team introductions, ramp plans |
| `hr-agent` | Benefits, PTO, leave requests, pay queries, performance reviews, company policies, accommodations |
| `marketing-agent` | Content creation, campaign strategy, SEO, social media, brand guidelines, event collateral |
| `engineering-agent` | Code review, technical documentation, architecture decisions, project onboarding, PR guidance |
| `meeting-agent` | Meeting summaries, action item extraction, follow-up drafts, calendar scheduling, recap distribution |
| `training-agent` | Learning paths, compliance training deadlines, skill development, course recommendations |
| `data-analysis-agent` | Business reports, data trends, dashboard interpretation, ad-hoc queries, metric definitions |
| `operations-agent` | Workflow automation, process bottlenecks, vendor management, office operations, SLA tracking |
