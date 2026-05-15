# Tools Reference — IT Help Desk Agent

## IT Service Management (ITSM)
- **ServiceNow (Healthcare IT edition)** — incident creation, ticket status updates, priority escalation, knowledge article search, SLA tracking, CI (configuration item) lookup, change request submission; REST API with service account credentials
- **Jira Service Management** — incident and request ticket management, queue assignment, SLA monitoring; REST API with service account

## Identity & Access Management
- **Microsoft Entra ID (Azure AD) Graph API** — user account status (enabled/disabled/locked), group memberships, last sign-in, MFA status, password expiration; read-only with service account (no password reset capability — routes to authorized IAM workflow)
- **Active Directory (on-premises LDAP / REST gateway)** — same lookups for on-premises AD; read-only access

## EHR System Health
- **Epic System Pulse / Epic Status Page** — Epic instance availability, active incidents, maintenance windows, scheduled downtime; REST API with Epic admin credentials
- **Cerner Lights On Network** — Cerner system performance metrics, response times, active incidents; API with Cerner credentials

## Monitoring & Alerting
- **PagerDuty** — active incident status, on-call schedules, escalation policy lookup, incident acknowledgment trigger; REST API with service account
- **Azure Monitor / Splunk** — system health dashboards, application error logs (sanitized, no PHI), infrastructure alerts; read-only REST API

## Remote Support
- **TeamViewer Healthcare / Cisco Webex Support** — remote desktop session initiation for non-EHR workstation issues; session token generated per-ticket with time-limited access

## Knowledge Base
- **ServiceNow Knowledge Base** — IT knowledge articles, known issue workarounds, standard operating procedures, Epic downtime procedures; REST search API

## Data Sources

### ITSM Ticket Data

- **ServiceNow** — ticket number, ticket type (incident/request/problem/change), short description, full description, caller (name, department, phone — treated as internal PII), assigned group, assigned technician, priority (1-4), state (new/in-progress/on-hold/resolved/closed), category (EHR/network/hardware/access/imaging/other), subcategory, affected CI (configuration item name, type), resolution notes, time opened, time resolved, SLA met flag, escalation history

### Identity & Access Status

- **Azure AD / Active Directory (read-only)** — UPN (userPrincipalName), display name, account enabled status, account lockout status (locked: yes/no), last failed sign-in timestamp, MFA enforced status, group memberships relevant to EHR role, manager UPN, department, job title; no passwords or credentials

### EHR System Status

- **Epic System Pulse** — component name (Epic Hyperspace, MyChart, Cogito, Bridges, etc.), status (operational/degraded/outage), incident title, incident description, start time, estimated resolution time, affected environments (production/test/training)
- **Cerner Lights On Network** — solution name, environment, availability %, response time (ms), active alert count, alert severity

### Infrastructure Monitoring (no PHI)

- **Azure Monitor / Splunk** — host name, application name, error code, error message text (sanitized), timestamp, severity level, alert rule name, affected service, ticket correlation ID

### Knowledge Articles

- **ServiceNow KB** — article number, title, category, valid from/to dates, content body, linked tickets (for known issue articles), view count, helpful vote count, author
