Available integrations for workflow automation, vendor management, and operations optimization:

- ServiceNow for process workflow tracking, SLA monitoring, and operational incident management
- Coupa or SAP Ariba for vendor contract status, purchase order history, and spend analytics (read-only)
- Workflow automation platforms (Zapier, Workato, or n8n) for triggering and monitoring automated process flows
- Jira or Asana for tracking operational project milestones, blockers, and cross-team dependencies
- Data warehouse read access for querying operational KPIs, cycle times, throughput metrics, and SLA attainment rates

## Data Sources

Systems and platforms accessed for operational workflow management, vendor oversight, SLA tracking, and process optimization.

### IT Service & Operations Management

- **ServiceNow** -- enterprise service management
  - **Incident**: sys_id, number, category, short_description, priority, state, assignment_group, sla_due, resolved_at, resolution_code, reopen_count
  - **SLA**: sla_id, name, target_resolution_time, breach_time, stage, paused, business_hours, triggered_on
  - **Change request**: change_id, number, type, short_description, state, risk, impact, planned_start, planned_end, assignment_group, approval_state
- **PagerDuty** -- incident response
  - **Incident**: incident_id, title, service, urgency, status, assigned_to, escalation_policy, triggered_at, resolved_at, MTTR
  - **Service**: service_id, name, status, escalation_policy, integrations, last_incident_at

### Procurement & Vendor Management

- **Coupa** -- business spend management
  - **Purchase order**: po_id, po_number, supplier, buyer, requested_by, line_items, total_amount, currency, status, created_at, approved_at, delivery_date
  - **Contract**: contract_id, name, supplier, start_date, end_date, value, status, auto_renew, owner, last_reviewed
  - **Invoice**: invoice_id, supplier, po_id, amount, currency, received_date, due_date, payment_status, approved_by
- **SAP Ariba** -- procurement and supply chain
  - **Requisition**: requisition_id, created_by, items, total_value, status, approvers, submitted_date, approved_date
  - **Vendor**: vendor_id, name, category, country, risk_score, certifications, payment_terms, preferred_status

### Workflow Automation

- **Workato** -- enterprise automation platform
  - **Recipe**: recipe_id, name, trigger, actions, status, last_run, run_count, error_count, created_at
  - **Job**: job_id, recipe_id, status, started_at, completed_at, steps_executed, error_message
- **Zapier** -- workflow automation
  - **Zap**: zap_id, name, trigger_app, action_apps, status, last_run, successful_runs, errored_runs

### Project & Process Management

- **Asana** -- work management
  - **Project**: project_id, name, owner, team, due_date, status, percent_complete, tasks_total, tasks_completed
  - **Task**: task_id, name, assignee, due_date, status, project, section, dependencies, created_at
- **Monday.com** -- work operating system
  - **Board**: board_id, name, type, owner, groups, columns, item_count, created_at, last_activity_at
  - **Item**: item_id, name, board_id, group_id, column_values, status, priority, owner, timeline_start, timeline_end

### Financial & Spend Analytics

- **Netsuite** -- ERP and financial management
  - **Vendor bill**: bill_id, vendor, amount, currency, due_date, status, account, department, approval_date, payment_date
  - **Budget**: budget_id, period, account, department, budget_amount, actual_amount, variance, percent_utilized
