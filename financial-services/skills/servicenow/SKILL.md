---
name: servicenow
description: ServiceNow IT service management platform; lets an agent create, update, route, and close IT incidents and fraud investigation cases, track SLA compliance, and retrieve asset and configuration records.
metadata: {"openclaw":{"requires":{"env":["SERVICENOW_INSTANCE_URL","SERVICENOW_CLIENT_ID","SERVICENOW_CLIENT_SECRET","SERVICENOW_API_USER","SERVICENOW_API_PASSWORD"]}},"primaryEnv":"SERVICENOW_INSTANCE_URL"}
---

# ServiceNow

## What it is
ServiceNow is the enterprise IT service management (ITSM) and workflow automation platform used across financial services firms to manage IT incidents, service requests, change management, and business-process case management. In this segment, it serves both the IT Help Desk agent (IT tickets and access requests) and the Fraud Detection agent (fraud investigation case lifecycle management).

## When to use this skill
- Create a new IT incident or service request ticket on behalf of a staff member
- Update an existing incident with investigation steps, evidence, or resolution notes
- Route a ticket or fraud case to the appropriate team or owner
- Check SLA compliance status and flag cases approaching breach
- Retrieve asset records and configuration items (CIs) for troubleshooting
- Manage change requests for access provisioning or system modifications
- Close a resolved case with disposition rationale and final notes

## Credentials
This skill authenticates using env vars declared in `metadata` above. Set them in `~/.openclaw/.env` (see `.env.example` at the config root). Required variables:
- `SERVICENOW_INSTANCE_URL` - ServiceNow instance base URL (e.g. `https://yourfirm.service-now.com`)
- `SERVICENOW_CLIENT_ID` - OAuth2 client ID for the integration application
- `SERVICENOW_CLIENT_SECRET` - OAuth2 client secret
- `SERVICENOW_API_USER` - Service account username (Basic Auth fallback)
- `SERVICENOW_API_PASSWORD` - Service account password (Basic Auth fallback)

## Key operations
- `POST /api/now/table/incident` — create a new incident record
- `GET /api/now/table/incident/{sys_id}` — retrieve incident details
- `PATCH /api/now/table/incident/{sys_id}` — update incident fields (state, notes, assignment)
- `POST /api/now/table/sn_si_incident` — create a security incident (fraud/SOC use cases)
- `GET /api/now/table/cmdb_ci` — retrieve configuration items from the CMDB
- `GET /api/now/table/task?sysparm_query=assigned_to=...` — list tasks assigned to a user or group

## Notes
- ServiceNow tables and fields are highly customized per deployment; confirm field names (e.g. `u_fraud_typology`) with your ServiceNow admin before wiring
- OAuth2 is preferred over Basic Auth; Basic Auth should be disabled in production instances per security policy
- ServiceNow enforces role-based access at the table level; the integration service account needs the `itil` role for incident management and a custom role for fraud case tables
- Sub-production environments (dev, test) are separate instances with independent URLs and credentials
