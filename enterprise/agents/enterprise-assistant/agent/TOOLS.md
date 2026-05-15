Available integrations for the enterprise entry-point orchestrator:

- sessions_spawn for delegating tasks to specialist subagents and collecting their responses
- Identity provider (Okta, Azure AD) for verifying employee identity and role-based access before routing
- Slack or Microsoft Teams for delivering responses and notifications in the employee's preferred channel
- ServiceNow for creating and tracking cross-functional service requests generated during a session
- Audit log write-back for recording delegation decisions and employee interactions for compliance review

## Data Sources

Systems and platforms accessed by the enterprise entry-point orchestrator for routing context and employee identity.

### Identity & Directory

- **Okta** -- workforce identity provider
  - **User profile**: user_id, email, display_name, department, job_title, manager_id, employment_status, groups
  - **Session**: session_id, user_id, login_time, ip_address, mfa_verified, risk_score
- **Azure Active Directory** -- Microsoft identity and directory
  - **User object**: object_id, upn, display_name, department, office_location, manager, assigned_licenses
  - **Group membership**: group_id, group_name, group_type, member_ids, dynamic_rule

### Communication Platforms

- **Slack** -- team messaging and workflow
  - **Message event**: channel_id, user_id, ts, text, thread_ts, attachments, bot_id
  - **Channel**: channel_id, name, is_private, members, topic, purpose
- **Microsoft Teams** -- enterprise collaboration
  - **Chat message**: message_id, channel_id, from_user, content, timestamp, importance, mentions
  - **Meeting**: meeting_id, organizer, attendees, scheduled_start, scheduled_end, recording_url

### Service Management

- **ServiceNow** -- IT and enterprise service management
  - **Incident**: sys_id, number, caller_id, category, short_description, priority, state, assigned_to, opened_at
  - **Request**: request_id, requested_for, cat_item, variables, approval_state, fulfillment_group, due_date

### Audit & Compliance

- **Splunk** -- security information and event management
  - **Audit event**: event_id, timestamp, user, action, resource, result, source_ip, session_id
  - **Alert**: alert_id, search_name, severity, triggered_at, result_count, owner
