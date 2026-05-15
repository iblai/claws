---
name: servicenow
description: FedRAMP-authorized ITSM platform; lets agents create/update incidents, service requests, change records, onboarding tasks, and security incidents, and search the knowledge base.
metadata: {"openclaw":{"requires":{"env":["SERVICENOW_INSTANCE_URL","SERVICENOW_CLIENT_ID","SERVICENOW_CLIENT_SECRET","SERVICENOW_API_VERSION"]}},"primaryEnv":"SERVICENOW_CLIENT_SECRET"}
---

# ServiceNow

## What it is
ServiceNow is the dominant IT Service Management (ITSM) and workflow platform used across federal and state agencies. Government deployments run on FedRAMP High-authorized infrastructure. It consolidates incident management, service requests, change management, onboarding workflows, and security operations into a single platform.

## When to use this skill
- Opening, updating, or resolving IT incidents and service requests (RITM)
- Tracking and updating onboarding task checklists across HR, IT, Facilities, and Security
- Creating or escalating security incidents with IOCs and containment notes
- Searching the knowledge base for approved workarounds and procedures
- Submitting emergency change requests or verifying approved maintenance windows

## Credentials
This skill authenticates using variables from the OpenClaw daemon env file `~/.openclaw/.env` (template: `.env.example`). Required variables:
- `SERVICENOW_INSTANCE_URL` - base URL of the agency ServiceNow instance (e.g., `https://agency.service-now.com`)
- `SERVICENOW_CLIENT_ID` - OAuth 2.0 client ID for the registered API application
- `SERVICENOW_CLIENT_SECRET` - OAuth 2.0 client secret
- `SERVICENOW_API_VERSION` - Table API version (default: `v2`)

## Key operations
- `GET /api/now/table/incident` — query incidents by number, caller, assignment group, or state
- `POST /api/now/table/incident` — create a new incident record
- `PATCH /api/now/table/incident/{sys_id}` — update incident state, work notes, or resolution code
- `GET /api/now/table/sc_request` — list service request records (RITM)
- `POST /api/now/table/sn_si_incident` — create a Security Operations security incident
- `GET /api/now/table/kb_knowledge` — search knowledge base articles
- `GET /api/now/table/change_request` — retrieve change records and CAB approval status

## Notes
- All write operations require the API user to hold the `itil` or `sn_incident_write` role; security incident creation requires `sn_si.analyst`.
- FedRAMP High instances are hosted at `*.service-now.com` with FedRAMP boundaries enforced; confirm your instance URL with the agency ISSO.
- Rate limit: 20,000 requests/hour per OAuth client by default; adjust via the agency System Throttle Rules table.
- Use the `sysparm_fields` query parameter to limit returned columns and reduce payload size.
