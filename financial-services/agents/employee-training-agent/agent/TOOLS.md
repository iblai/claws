# Tools Reference — Training Coordinator

## Learning Management Systems

- **Cornerstone OnDemand** — manage training assignments, retrieve completion status and scores, pull certification records and expiration dates, generate compliance training reports by department and regulation, send automated reminders
- **SAP SuccessFactors Learning** — access mandatory regulatory training tracks, retrieve completion data by employee, pull FINRA and securities law module assignments, manage onboarding curricula for new hires and role transfers
- **Litmos (SAP)** — deploy compliance course content, track module completion and pass/fail scores, retrieve certificate URLs, manage recurrence rules for annual certifications

## FINRA Continuing Education

- **FINRA CE Portal API** — retrieve each registered representative's Regulatory Element completion status and due date; pull Firm Element training needs analysis outputs; confirm completed CE credits against FINRA records
- **FINRA BrokerCheck** — verify current registration status and license type for CE requirement mapping

## Security Awareness

- **KnowBe4** — manage phishing simulation campaigns, retrieve click rates and failure data, assign remedial training modules, pull compliance training completion for security awareness programs

## HR and HRIS Integration

- **Workday HCM** — retrieve employee roster, job code, department, hire date, and role-change history for training assignment logic; pull manager hierarchy for escalation routing
- **ADP / Payroll System** — confirm new hire start dates and termination dates to trigger onboarding and offboarding training workflows

## Notifications

- **Notification Service** — send certification expiration reminders (60/30/7-day cadences) and non-compliance escalations to employees, managers, and the CCO via the firm's approved communication channel

## Data Sources

### Learning Management System

- **Cornerstone OnDemand** — training assignments (assignment ID, employee ID, course ID, regulation, assigned date, due date, completion status, overdue flag, escalation level), completion records (completion ID, employee, course, completion date, score, attempts, pass/fail, certificate URL, audit trail hash), certification tracking (cert ID, employee, certification name, issue date, expiration date, renewal requirements, status, grace period)
- **SAP SuccessFactors Learning** — mandatory training records (regulation code, jurisdiction, required courses, target audience, assignment frequency, completion window, completion rate), compliance dashboards (metric, period, compliance rate by department, overdue count, expiring-soon count, manager escalation status)
- **Litmos** — course library (course ID, regulation, jurisdiction, topic, duration, format, version, last updated, passing threshold), automated assignment rules (rule ID, trigger criteria, population, course, due date calculation, recurrence, notification schedule)

### FINRA Continuing Education

- **FINRA CE Tracking** — Regulatory Element (representative ID, rep name, license type, CRD number, CE due date, completion status, waiver flag), Firm Element needs analysis (NCA year, topic, learning objectives, assigned population, completion rate), CE audit log (event type, representative, action, timestamp, learning credits)
- **FINRA BrokerCheck Records** — registration data (rep name, CRD number, firm, license types, registration state, status, disclosure events)

### Employee Records

- **Workday HCM** — employee roster (employee ID, name, department, job code, manager, hire date, office location, employment status), role changes (employee ID, prior role, new role, effective date, manager, training reassignment trigger), terminations (employee ID, termination date, exit type, offboarding training status)

### Security Awareness

- **KnowBe4** — phishing simulations (campaign ID, template, target count, sent date, click count, report count, click rate, repeat offenders), security training (module ID, regulation, assigned population, completion date, score, certificate, remedial training flag)

### Audit Trail

- **Training Audit Log** — (event type — assigned/completed/expired/escalated/waived, employee ID, course ID, timestamp, operator ID, regulatory reference, certificate hash, manager notification sent)
