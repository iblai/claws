Available integrations for HR policy, benefits, and people operations:

- Workday HCM or SAP SuccessFactors for employee records, leave balances, and compensation data (read-only)
- Benefits administration platform (Benefitfocus, bswift) for plan details, enrollment windows, and cost information
- Document management system for fetching the current employee handbook and policy PDFs with version metadata
- Case management via ServiceNow HR Service Delivery for logging inquiries and routing escalations to HR Business Partners
- Payroll system read-only access for answering basic pay stub and deduction questions

## Data Sources

Systems and platforms accessed for HR policy guidance, benefits administration, and people operations support.

### Human Resource Information Systems

- **Workday HCM** -- unified HR platform
  - **Employee record**: worker_id, legal_name, preferred_name, hire_date, employment_status, job_title, department, location, cost_center, manager_id
  - **Leave balance**: plan_name, accrued_hours, used_hours, available_hours, carryover, policy_cap, forfeiture_date
  - **Job history**: position_id, job_title, department, effective_date, reason, manager, base_salary, grade
- **SAP SuccessFactors** -- enterprise HR suite
  - **Employee central**: person_id, employment_record, job_info, compensation_info, pay_component_details
  - **Time off**: leave_type, balance, accrual_rate, request_history, approval_chain, policy_name

### Benefits Administration

- **Benefitfocus** -- benefits enrollment platform
  - **Enrollment**: plan_year, elected_plans, coverage_tier, annual_cost, employer_contribution, employee_premium, dependent_coverage
  - **Plan detail**: plan_name, type, deductible, out_of_pocket_max, copay, coinsurance, network, prescription_tiers
- **ADP Benefits** -- payroll-integrated benefits
  - **FSA/HSA account**: account_type, election_amount, ytd_contributions, claims_submitted, available_balance, rollover_limit

### Policy & Compliance

- **Mineral (formerly ThinkHR)** -- HR compliance library
  - **Policy template**: policy_area, template_version, jurisdiction, last_updated, compliance_notes, required_sections
  - **Compliance update**: regulation, effective_date, impact_areas, required_actions, jurisdiction
- **PolicyTech** -- policy lifecycle management
  - **Policy**: policy_id, title, version, status, owner, effective_date, review_date, category, geographic_scope, acknowledgment_required

### Performance Management

- **Lattice** -- performance and engagement
  - **Review cycle**: cycle_id, name, review_type, start_date, end_date, status, participants, rating_scale
  - **Goal**: goal_id, title, key_results, owner, team, status, due_date, progress_percent, aligned_to
- **Workday Performance** -- performance reviews
  - **Review form**: review_id, template, period, employee_id, manager_id, competency_ratings, goal_ratings, overall_rating, status

### Case Management

- **ServiceNow HR Service Delivery** -- HR case management
  - **Case**: case_id, employee_id, category, subcategory, description, priority, assigned_agent, status, sla, resolution, satisfaction_rating
  - **Knowledge article**: kb_id, title, category, body, view_count, helpfulness_rating, last_updated
