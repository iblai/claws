Available integrations for IT help desk and issue resolution:

- ServiceNow ITSM for creating, updating, and resolving incidents, service requests, and change records
- Okta and Azure AD for user account management, password resets, MFA enrollment, and access provisioning
- Jira Service Management as an alternative ticketing platform for engineering-integrated teams
- MDM platforms (Jamf, Intune) for device enrollment status, compliance posture, and remote wipe initiation
- Status page integrations (Statuspage.io, Atlassian Status) for checking known outages before troubleshooting

## Data Sources

Systems and platforms accessed for IT issue resolution, access management, and device support.

### IT Service Management

- **ServiceNow** -- enterprise ITSM platform
  - **Incident**: sys_id, number, caller_id, category, subcategory, short_description, priority, state, assigned_to, assignment_group, opened_at, resolved_at, resolution_code, resolution_notes
  - **Service request**: request_id, requested_for, cat_item, variables, approval_state, fulfillment_group, sla_due, state
  - **Knowledge article**: kb_id, title, category, body, author, view_count, rating, last_updated, active
- **Jira Service Management** -- developer-centric ITSM
  - **Issue**: issue_id, key, summary, description, issue_type, priority, status, assignee, reporter, created, updated, resolution, components, labels

### Identity & Access Management

- **Okta** -- identity and access management
  - **User**: user_id, login, email, first_name, last_name, status, created, last_login, mfa_enrolled, password_changed, groups
  - **Application assignment**: app_id, app_name, user_id, status, last_sync, profile
  - **MFA factor**: factor_id, user_id, factor_type, provider, status, created, last_updated
- **Azure Active Directory** -- Microsoft IAM
  - **User**: object_id, upn, display_name, account_enabled, last_sign_in, license_assignments, group_memberships, mfa_status
  - **Conditional access policy**: policy_id, name, state, conditions, grant_controls, session_controls

### Device Management

- **Jamf Pro** -- Apple device management (MDM)
  - **Device**: device_id, serial_number, model, os_version, enrolled_date, last_check_in, compliance_status, managed_status, username, site
  - **Policy**: policy_id, name, category, scope, frequency, packages, scripts, triggers
- **Microsoft Intune** -- unified endpoint management
  - **Device**: device_id, device_name, os, os_version, compliance_state, last_sync, enrolled_by, management_agent, aad_registered

### Network & Infrastructure

- **PagerDuty** -- incident alerting and on-call management
  - **Incident**: incident_id, title, service, urgency, status, assigned_to, triggered_at, resolved_at, escalation_policy
  - **Alert**: alert_id, summary, severity, service, source, dedup_key, created_at
- **Datadog** -- infrastructure monitoring
  - **Monitor**: monitor_id, name, type, query, status, tags, last_triggered, message, priority
  - **Event**: event_id, title, text, date_happened, priority, source, tags, host, device
