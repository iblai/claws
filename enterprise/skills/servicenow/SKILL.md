---
name: servicenow
description: ServiceNow ITSM and enterprise service management - lets an agent create, read, update, and route incidents, service requests, HR cases, change records, and knowledge articles.
metadata: {"openclaw":{"requires":{"env":["SERVICENOW_INSTANCE_URL","SERVICENOW_USERNAME","SERVICENOW_PASSWORD"]}},"primaryEnv":"SERVICENOW_INSTANCE_URL"}
---

# ServiceNow

## What it is
ServiceNow is the dominant enterprise service management platform, used across IT, HR, facilities, and operations to track incidents, service requests, and workflow approvals. In this segment it acts as the cross-functional ticketing backbone for IT help desk, HR case management, employee onboarding provisioning, and operational SLA tracking. Agents use it to open tickets on behalf of employees, check resolution status, and surface knowledge articles.

## When to use this skill
- Creating an incident or service request on behalf of an employee
- Checking the status or resolution notes on an existing ticket
- Routing an HR inquiry to the HR Service Delivery module
- Submitting an access provisioning or equipment request for a new hire
- Fetching knowledge articles relevant to an employee's issue before escalating

## Credentials
This skill authenticates using variables from `~/.openclaw/.env` (template: `.env.example` at the config root). Required variables:
- `SERVICENOW_INSTANCE_URL` - full instance base URL (e.g. `https://mycompany.service-now.com`)
- `SERVICENOW_USERNAME` - service account username
- `SERVICENOW_PASSWORD` - service account password

## Key operations
- `GET /api/now/table/incident?sysparm_query=...` - query incidents by filter
- `POST /api/now/table/incident` - create a new incident
- `PATCH /api/now/table/incident/{sys_id}` - update incident fields
- `GET /api/now/table/sc_request/{sys_id}` - retrieve a service request
- `POST /api/now/table/sc_req_item` - submit a catalog item request
- `GET /api/now/table/kb_knowledge?sysparm_query=text=...` - search knowledge base

## Notes
- Use basic auth or OAuth 2.0 (configure OAuth app in ServiceNow if available).
- The Table API is the standard REST interface; avoid legacy SOAP endpoints.
- `sys_id` is the internal 32-char GUID; prefer to query by `number` (e.g., INC0012345) for human-readable lookups.
- Dev/test instances use separate URLs; never write to production from a non-production agent config.
- Rate limiting is enforced per instance; default is 3,000 requests per 5 minutes per user.
