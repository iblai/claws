Available integrations for customer support ticket resolution and follow-up:

- Zendesk or Salesforce Service Cloud for ticket creation, updates, macros, and CSAT surveys
- Freshdesk as an alternative helpdesk for ticket management, canned responses, and SLA tracking
- Salesforce CRM for customer account history, entitlements, and contract details
- Intercom for live chat session context and customer messaging history
- Jira for linking support tickets to engineering bug reports and feature request tracking

## Data Sources

Systems and platforms accessed for customer support ticket resolution, account management, and escalation handling.

### Helpdesk Platforms

- **Zendesk** -- customer service and ticketing
  - **Ticket**: ticket_id, requester_id, assignee_id, group_id, subject, description, status, priority, type, tags, channel, created_at, updated_at, solved_at, satisfaction_rating
  - **User**: user_id, name, email, organization_id, role, phone, time_zone, locale, created_at, notes, tags
  - **Organization**: org_id, name, domain, tags, external_id, group_id, shared_tickets, notes
- **Salesforce Service Cloud** -- enterprise customer service
  - **Case**: case_id, case_number, account_id, contact_id, subject, description, type, status, priority, reason, origin, owner_id, created_date, closed_date, resolution
  - **Entitlement**: entitlement_id, account_id, name, type, start_date, end_date, sla_process, business_hours

### Customer Success & CRM

- **Gainsight** -- customer success platform
  - **Customer**: customer_id, name, csm_owner, health_score, tier, arr, renewal_date, nps_score, risk_reason, lifecycle_stage
  - **Success plan**: plan_id, customer_id, objective, status, due_date, owner, tasks_completed, tasks_total
  - **Timeline activity**: activity_id, customer_id, type, date, subject, csm, sentiment, is_risk_flag
- **Totango** -- customer success tracking
  - **Account**: account_id, name, segment, health, usage_score, adoption_score, renewal_score, owner, contract_value

### Live Chat & Messaging

- **Intercom** -- customer messaging platform
  - **Conversation**: conversation_id, contact_id, assignee, state, read, created_at, updated_at, channel, tags, priority, source_type
  - **Contact**: contact_id, name, email, phone, last_seen_at, session_count, location, os, browser, custom_attributes
- **Freshdesk** -- cloud helpdesk
  - **Ticket**: ticket_id, requester_id, email, subject, description, status, priority, source, tags, created_at, resolved_at, csat_score, agent_id, group_id

### Product Usage Analytics

- **Mixpanel** -- product analytics
  - **Event**: event_name, distinct_id, time, properties, user_properties, session_id, platform
  - **User profile**: distinct_id, name, email, created, last_login, plan, usage_events_30d
- **Amplitude** -- digital analytics
  - **User activity**: user_id, event_type, event_time, session_id, platform, version, feature_flags, event_properties
