---
name: servicenow
description: ServiceNow (Healthcare IT) — lets an agent create, update, and query IT service management tickets, knowledge articles, and configuration items within a ServiceNow instance deployed in a health system.
metadata: {"openclaw":{"requires":{"env":["SERVICENOW_CLIENT_ID","SERVICENOW_INSTANCE_URL","SERVICENOW_CLIENT_SECRET","SERVICENOW_SERVICE_ACCOUNT"]}},"primaryEnv":"SERVICENOW_CLIENT_ID"}
---

# ServiceNow

## What it is
ServiceNow is the leading ITSM platform in enterprise healthcare IT, used to manage incidents, service requests, changes, and knowledge articles across clinical and administrative technology environments. Healthcare-specific editions include pre-built workflows for EHR downtime procedures, access request routing, and HIPAA-aware audit trails. Agents use the REST Table API to automate tier-1 help desk triage, ticket creation, status lookups, and knowledge base searches.

## When to use this skill
- Create a new incident ticket when a user reports a system issue (EHR unavailability, login failure, device malfunction)
- Look up the status or resolution notes of an existing ticket by number
- Search the knowledge base for known issue workarounds or EHR downtime procedures
- Escalate a ticket priority or reassign it to a specialized support group
- Query configuration item (CI) details (server, application, workstation) linked to an incident

## Credentials
This skill authenticates using variables declared in the metadata above. Copy `~/.openclaw/.env.example` to `~/.openclaw/.env` and fill in real values. Required variables:
- `SERVICENOW_INSTANCE_URL` - full instance URL (e.g., `https://healthsystem.service-now.com`)
- `SERVICENOW_CLIENT_ID` - OAuth 2.0 client ID registered in ServiceNow
- `SERVICENOW_CLIENT_SECRET` - OAuth 2.0 client secret for token exchange
- `SERVICENOW_SERVICE_ACCOUNT` - service account username for fallback basic auth (non-PHI operations)

## Key operations
- `GET /api/now/table/incident?number={INC#}` — retrieve incident by ticket number
- `POST /api/now/table/incident` — create new incident ticket with caller, description, category, priority
- `PATCH /api/now/table/incident/{sys_id}` — update ticket fields (state, priority, work notes, assignment group)
- `GET /api/now/table/kb_knowledge?sysparm_query=short_description CONTAINS {query}` — search knowledge articles
- `GET /api/now/table/cmdb_ci?name={ci_name}` — look up configuration item details
- `GET /api/now/table/sc_request?opened_by={user}` — list service requests by requester

## Notes
- ServiceNow REST API uses `sys_id` (internal GUID) for record references; the ticket number (INC0001234) is a display field requiring a lookup step.
- Do not log PHI in ticket descriptions; reference patient by encounter ID token only.
- Rate limit: 2,000 API calls/hour per instance; throttled per OAuth token.
- Use the `sysparm_fields` parameter to restrict response payload to only needed fields.
- Healthcare instances may enforce IP allowlisting; coordinate with the health system IT security team before adding agent IP ranges.
