# Data Sources

Systems and platforms commonly accessed for employee onboarding.

## Human Resource Information Systems (HRIS)

- **Workday HCM** -- new hire records (employee ID, legal name, preferred name, email, start date, location, job profile, pay group), position details (position ID, title, department, cost center, supervisory org, job family, grade level), org structure (reporting hierarchy, supervisory orgs, department tree, matrix relationships), benefits eligibility (benefit plans, eligibility date, enrollment window, dependent info, life event triggers), personal information (address, phone, emergency contacts, tax withholding elections, direct deposit, I-9 status)
- **SAP SuccessFactors** -- employee master data (person ID, employment record, job info, compensation info, personal info, national IDs), onboarding workflows (process ID, task list, task owner, due dates, completion status, dependencies), digital forms (form ID, form type, field values, signatures, submission date, approval status), compliance tasks (task ID, regulation, jurisdiction, due date, completion evidence, audit trail)
- **Oracle HCM Cloud** -- hire actions (action ID, action type, effective date, reason code, position, department, approval chain), position management (position ID, incumbent, FTE, budget, headcount, location), onboarding checklists (checklist ID, tasks, assignee, category, status, due date, completed date, comments)
- **BambooHR** -- new hire tracking (employee ID, name, start date, department, location, employment status, offer details), document signing (document ID, signer, template, status, signed date, IP address), onboarding task lists (task ID, assignee, category, due date, status, notes), employee directory (name, photo, title, department, location, phone, email, reports-to)
- **ADP Workforce Now** -- payroll setup (employee ID, pay frequency, pay type, salary/rate, deductions, tax elections, direct deposit), tax forms (W-4 federal withholding, state withholding, local tax elections, filing status, allowances), benefits enrollment (plan selections, coverage level, effective date, dependent enrollment, beneficiary designations), time tracking setup (time policy, schedule, overtime rules, accrual policies, time zone)
- **UKG Pro (Kronos)** -- employee records (employee ID, demographic data, job record, compensation, organizational assignment), scheduling setup (schedule pattern, shift assignments, availability, time zone, labor allocation), time and attendance configuration (punch rules, rounding rules, overtime policy, meal/break rules, exception handling)

## Onboarding & Workflow Platforms

- **Click Boarding** -- guided onboarding workflows (workflow ID, steps, task type, assignee, due date, completion percentage), task management (task ID, category, description, owner, status, dependencies, reminders), compliance forms (form type, jurisdiction, fields, e-signature status, submission date, storage location), new hire portal (portal access, welcome content, resource links, contact directory, progress tracker)
- **Sapling (now Kallidus)** -- onboarding workflows (workflow ID, template, tasks, milestones, assigned roles, SLA), people operations automation (trigger events, automated actions, notification rules, escalation paths), IT provisioning triggers (systems to provision, access levels, equipment requests, license assignments, approval workflow)
- **Enboarder** -- experience-driven onboarding (journey ID, touchpoints, content blocks, timing, personalization rules), manager coaching prompts (prompt ID, timing, suggested actions, manager ID, completion status), stakeholder nudges (stakeholder role, nudge type, timing, message template, delivery channel, response tracking)
- **Talmundo** -- pre-boarding content (content ID, type, target audience, release schedule, engagement tracking), onboarding journeys (journey ID, phases, milestones, activities, duration, completion criteria), feedback collection (survey ID, timing, questions, responses, sentiment score, NPS)

## Identity & Access Provisioning

- **Microsoft Entra ID (Azure AD)** -- account creation (user principal name, display name, mail nickname, department, job title, manager), group assignments (group ID, group type, membership type, role, access scope), license provisioning (license SKU, service plans, assignment date, usage location), MFA setup (authentication methods, phone number, authenticator app, FIDO2 keys, default method)
- **Okta** -- SSO access (user ID, assigned apps, authentication policy, session settings, login history), application assignments (app ID, app name, assignment type, profile mapping, provisioning status), lifecycle management (lifecycle state, activation date, suspension triggers, deprovisioning rules, grace period)
- **SailPoint / Saviynt** -- identity governance (identity ID, identity attributes, certifications, access reviews, risk score), access request workflows (request ID, requested access, justification, approver chain, SLA, status), role-based provisioning (role ID, entitlements, auto-assignment rules, segregation-of-duty policies, provisioning targets)

## Document & Compliance

- **DocuSign / Adobe Sign** -- offer letters (document ID, template, recipient, sent date, signed date, envelope status), tax forms W-4/I-9 (form type, field values, signature, submission date, verification status, storage reference), NDAs and policy acknowledgments (document type, version, signer, signed date, countersigner, retention policy)
- **E-Verify** -- employment eligibility verification (case number, employee name, SSN last 4, document type, case status, result, created date, photo match), case management (case ID, status transitions, tentative non-confirmation, referral date, resolution)
- **Equifax Workforce Solutions** -- employment verification (employer, dates of employment, job title, salary, verification requestor), income verification (annual salary, pay frequency, YTD earnings, verification date), I-9 management (form version, section completion status, document type, expiration date, reverification schedule)

## IT & Equipment

- **ServiceNow** -- equipment requests (request ID, item, configuration, requestor, approver, fulfillment status, SLA), software provisioning (software name, license type, installation method, configuration, access level), access requests (system, access level, justification, approver, provisioning status, expiration), onboarding tickets (ticket ID, category, priority, assigned group, SLA, status, resolution)
- **JAMF / Intune** -- device enrollment (device ID, serial number, model, OS version, enrollment date, management profile), MDM policies (policy ID, settings, compliance status, enforcement mode, applicable devices), software deployment (app name, version, deployment method, installation status, required/available)
- **Oomnitza / Asset Panda** -- IT asset assignment (asset ID, asset type, serial number, assigned user, assignment date, condition), asset tracking (location, status, warranty expiration, purchase date, cost center, depreciation), asset retrieval (retrieval request, scheduled date, return condition, data wipe status)

## Learning & Training

- **Cornerstone / Workday Learning / Docebo** -- required onboarding courses (course ID, title, type, due date, compliance requirement, estimated duration), compliance training (regulation, jurisdiction, training module, completion deadline, recurrence), role-specific learning paths (path ID, role, department, courses, sequence, estimated total hours)
- **Lessonly (now Seismic Learning)** -- onboarding lessons (lesson ID, title, content type, estimated duration, assigned group), practice exercises (exercise ID, scenario, rubric, submission type, scoring criteria), knowledge checks (quiz ID, questions, passing score, attempts allowed, results, remediation path)

## Communication & Culture

- **Slack / Microsoft Teams** -- workspace and channel provisioning (workspace ID, channels to join, channel type, auto-join rules, welcome message), welcome messages (message template, sender, timing, personalization tokens, delivery confirmation), buddy matching (new hire ID, buddy ID, matching criteria, program duration, check-in schedule)
- **Confluence / Notion / SharePoint** -- company wiki (space ID, key pages, navigation structure, required reading list), policy documents (document ID, title, version, acknowledgment required, effective date), team handbooks (handbook ID, team, sections, last updated, owner), SOPs (procedure ID, title, steps, owner, review date, applicable roles)
