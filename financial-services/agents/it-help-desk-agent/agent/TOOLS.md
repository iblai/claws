# Tools Reference — IT Help Desk

## ITSM Platform

- **ServiceNow** — create, update, and close IT service tickets; route incidents to the appropriate team; track SLA compliance; pull asset records and configuration items (CIs); manage change requests for access modifications
- **Jira Service Management** — log and track technical issues; manage queues by priority and team; link incidents to known errors or problem records; retrieve service catalog items for standard access requests

## Identity and Access Management

- **Okta** — provision and deprovision user accounts; manage MFA enrollment status; retrieve user authentication logs; reset account credentials (with manager approval); manage application assignment and group membership
- **Microsoft Active Directory** — manage on-premises user account lifecycle; retrieve group memberships; reset passwords (with verified identity); provision and deprovision access to network shares and on-premise applications
- **CyberArk Privileged Access Management** — retrieve privileged account checkout logs; manage access requests to privileged accounts (domain admin, server admin, DBA); ensure just-in-time access provisioning for elevated permissions

## Endpoint and Security Monitoring

- **CrowdStrike Falcon** — retrieve endpoint detection alerts; pull quarantine status for flagged files; access device health and sensor status; triage endpoint security incidents and escalate to Information Security
- **Splunk SIEM** — query authentication logs, network traffic events, and endpoint activity for security incident investigation; correlate events across sources for threat hunting support
- **Cisco SecureX / Umbrella** — retrieve DNS security alerts and blocked domain requests; access network visibility data for VPN and remote access troubleshooting

## Financial Services Tools Support

- **Bloomberg Terminal** — guide staff through Bloomberg connectivity issues, BPIPE API troubleshooting, and terminal license resets; escalate hardware replacement requests to the vendor portal
- **FactSet Client Portal** — assist with login issues, permission requests, and data feed connectivity; submit support tickets to FactSet directly for unresolved issues

## Data Sources

### ITSM

- **ServiceNow** — incident records (ticket ID, caller, category, subcategory, priority, state, assignment group, assigned to, opened date, resolved date, resolution notes, SLA status, reopen count), change records (change ID, type, requester, approver, implementation window, affected CI, rollback plan, status), CMDB (CI ID, CI name, class, owner, location, status, manufacturer, model, support group, linked incidents)
- **Jira Service Management** — request records (issue ID, requester, request type, summary, description, priority, status, assignee, created, resolved, linked issues), knowledge base articles (article ID, title, category, solution steps, created by, last updated, view count)

### Identity and Access Management

- **Okta** — user records (user ID, display name, email, login, status, department, manager, created date, last login, MFA enrolled, MFA factors, app assignments), application assignments (user ID, application, assigned date, access level, last used), authentication logs (user, IP, device, timestamp, event type, outcome, risk level, MFA challenge outcome)
- **Microsoft Active Directory** — user accounts (sAMAccountName, UPN, display name, department, manager, OU, group memberships, last logon, account enabled, password last set, account locked status), group records (group name, type, scope, members, owner, description, OU)
- **CyberArk** — privileged access records (account ID, account name, system, platform, last password change, checked-out by, checkout time, check-in time, session recording available), access request log (request ID, requester, account, justification, approver, approval date, access window, session log reference)

### Security Monitoring

- **CrowdStrike Falcon** — endpoint alerts (device ID, hostname, user, alert type, severity, tactic, technique, status, first seen, last seen, remediation status), device inventory (device ID, hostname, OS, last seen, agent version, prevention policy, sensor status)
- **Splunk SIEM** — security events (source, event type, user, IP, timestamp, action, outcome, raw log excerpt), authentication failures (user, IP, timestamp, failure reason, failure count, account lockout trigger)

### Audit Trail

- **Access Change Log** — (event type — provisioned/modified/deprovisioned/password reset/MFA enrolled, user ID, system, access level, requestor, approver, manager approval reference, timestamp, ticket ID)
- **IT Incident Log** — (ticket ID, category, user affected, system, severity, resolution actions, resolver ID, open time, close time, SLA met, root cause category)
