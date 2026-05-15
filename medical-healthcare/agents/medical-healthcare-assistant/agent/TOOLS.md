# Tools Reference — Care Assistant (Parent)

The Care Assistant does not perform deep domain work directly; it routes. The following integrations are available at the parent layer for context-gathering and session handoff.

## EHR Identity Lookup
- **Epic MyChart / FHIR R4 API** — read-only patient demographics and active encounter context to validate session scope before routing; no clinical data modification at this layer
- **Cerner Millennium FHIR API** — same scope as Epic: demographics and encounter ID for routing context only

## Session Management
- **sessions_spawn (NemoClaw built-in)** — delegates work to specialist subagents; used for every non-trivial clinical, coding, compliance, or administrative request
- **OpenClaw Gateway API** — introspects available subagent status and health before spawning

## Directory / Staff Lookup
- **Azure Active Directory / Entra ID** — resolves authenticated user to role (physician, nurse, coder, admin) to inform routing logic
- **LDAP / Active Directory** — fallback role resolution for on-premises deployments

## Audit & Logging
- **Splunk / Azure Monitor** — write routing decision audit events (agent ID, intent classification, subagent spawned, timestamp); no PHI in log payloads

## Data Sources

The parent agent consumes only the minimal context needed to route requests correctly. Full domain data is accessed by specialist subagents after delegation.

### Identity & Role Context

- **Azure Active Directory / Entra ID** — user principal name, display name, department, job title, group memberships (role), last sign-in timestamp
- **LDAP directory** — uid, cn, departmentNumber, title, memberOf groups

### Active Session / Encounter Context

- **Epic FHIR R4 (read-only)** — Patient.id (masked token), Encounter.id, Encounter.class (inpatient/outpatient/ED), Encounter.status, Encounter.serviceType; used only to scope routing decisions
- **Cerner Millennium FHIR R4 (read-only)** — same fields as Epic for Cerner-hosted deployments

### Routing Telemetry

- **OpenClaw Gateway** — subagent availability status (id, healthy, current_load), recent session summaries (session_id, spawned_agent, intent_label, duration_ms, outcome_status); no PHI
- **Audit Log Store (Splunk / Azure Monitor)** — write-only: routing_event records (timestamp, user_role_hash, intent_classification, target_agent_id, session_id)
