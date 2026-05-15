Available integrations for the Agency Assistant (parent/router) agent:

- **sessions_spawn** — spawn a specialist subagent by id; pass context and user intent; collect and synthesize the returned result
- **Agency portal API** — read-only access to constituent-facing service catalog and status board for initial triage
- **Identity provider (SSO)** — verify session identity and role (employee vs. constituent) to route appropriately
- **Audit log writer** — append delegation events to the workspace audit trail for records compliance
- **Knowledge base (read-only)** — retrieve top-level FAQ answers for simple, self-contained questions that do not require specialist delegation

## Data Sources

Data the Agency Assistant accesses for triage and routing decisions.

### Session & Identity

- **Agency SSO / Identity Provider** — user session (session token, authenticated user ID, role: employee/manager/administrator/constituent, department, clearance level), authentication events (login timestamp, MFA method, session duration, logout event)

### Service Catalog

- **Agency Portal** — service directory (service name, owning department, description, eligibility criteria, online availability, average processing time, required documents, fee schedule), status board (service availability: online/degraded/offline, planned maintenance windows, outage messages, last updated timestamp)

### Audit & Routing

- **Workspace audit log** — delegation record (timestamp, user session ID, intent classification, subagent id dispatched, duration, outcome: success/escalation/error), interaction summary (conversation ID, turn count, topic tags, satisfaction signal if provided)
