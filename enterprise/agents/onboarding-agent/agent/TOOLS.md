Available integrations for new hire onboarding and ramp-up coordination:

- Workday or BambooHR for retrieving new hire records, start dates, role details, and checklist status
- Greenhouse or Lever for pulling pre-boarding data including offer details and candidate profile
- LMS platform (Cornerstone, Docebo, or internal) for enrolling new hires in required training paths
- Slack or Microsoft Teams for sending welcome messages, channel recommendations, and reminder notifications
- ServiceNow for submitting access provisioning requests and tracking equipment delivery status

## Data Sources

Systems and platforms accessed for new hire onboarding, ramp-up planning, and access provisioning coordination.

### HRIS & Pre-boarding

- **Workday HCM** -- employee data and onboarding workflows
  - **New hire**: worker_id, legal_name, preferred_name, start_date, job_title, department, location, manager_id, employment_type, cost_center
  - **Onboarding task**: task_id, worker_id, task_name, category, due_date, status, assigned_to, completion_date
- **BambooHR** -- SMB-focused HR and onboarding
  - **Employee**: employee_id, first_name, last_name, email, department, division, location, hire_date, reports_to, employment_status
  - **Onboarding checklist**: checklist_id, employee_id, item_name, due_date, completed, completed_date, assigned_owner

### Applicant Tracking & Recruiting

- **Greenhouse** -- talent acquisition platform
  - **Application**: application_id, candidate_id, job_id, status, applied_at, offer_sent_date, offer_accepted_date, start_date, hiring_manager_id
  - **Candidate profile**: candidate_id, first_name, last_name, email, phone, linkedin_url, resume_url, source
- **Lever** -- modern ATS and CRM
  - **Opportunity**: opportunity_id, candidate_name, stage, job, team, location, owner, created_at, archived_reason, offer_status

### Learning & Development

- **Cornerstone OnDemand** -- enterprise LMS
  - **Learning assignment**: assignment_id, employee_id, course_id, course_title, due_date, status, completion_date, score, required_flag
  - **Course**: course_id, title, category, duration, delivery_type, created_by, last_updated, compliance_required
- **Docebo** -- cloud LMS
  - **Enrollment**: enrollment_id, user_id, course_id, status, enrolled_date, completion_date, score, certificate_issued

### Communication & Collaboration

- **Slack** -- team messaging
  - **Channel**: channel_id, name, is_private, purpose, topic, member_count, recommended_for_roles
  - **Workspace user**: user_id, display_name, real_name, email, title, department, timezone
- **Microsoft Teams** -- enterprise communication
  - **Team**: team_id, display_name, description, owner, members, channels, guest_settings
  - **Channel**: channel_id, display_name, description, team_id, member_count, tabs

### Equipment & Access Provisioning

- **ServiceNow** -- IT service management
  - **Request**: request_id, requested_for, cat_item, variables, submitted_at, approval_state, fulfillment_group, due_date, state
  - **Hardware asset**: asset_id, serial_number, model, assigned_to, location, status, purchase_date, warranty_expiry
