Available integrations for government employee onboarding:

- **HRIS (Workday / PeopleSoft)** — retrieve new hire record, appointment details, effective date, supervisor, and duty station; track personnel action completion; submit access provisioning requests linked to the position
- **OPM e-QIP / eOD** — monitor background investigation form submission status (SF-85/SF-85P/SF-86), completion percentage, and adjudication status
- **ServiceNow onboarding workflows** — create and track onboarding task tickets across HR, IT, Facilities, and Security; update checklist item status; trigger cross-functional provisioning requests
- **Identity & access provisioning (Entra ID / Active Directory)** — initiate network account creation, PIV/CAC enrollment scheduling, and role-based access provisioning requests pending security clearance and manager approval
- **Benefits enrollment portal (Employee Express / BENEFEDS)** — provide new employee benefits election guides, enrollment deadlines by appointment type, and plan comparison links
- **Policy acknowledgment system** — present and record e-signature acknowledgments for IT acceptable use, ethics pledge, records management policy, and security awareness policy
- **Facilities / building access system** — submit badge issuance request, retrieve facility access instructions, and track PIV-linked physical access provisioning

## Data Sources

Systems and platforms for new employee onboarding in a government agency.

### New Hire Record

- **HRIS** — new hire profile (employee ID, name, appointment type: career/career-conditional/term/temporary/SES, position number, series, grade, pay plan, duty station, start date, supervisor, org code, appointment authority, citizenship status, veterans preference, telework eligibility), personnel action status (SF-52 number, NOA, effective date, approval chain status)

### Background Investigation

- **OPM e-QIP / eOD** — investigation package (package ID, investigation type: Tier 1/2/3/4/5, submission date, completion percentage, return for correction flag, submission date, OPM receipt confirmation, adjudication status: pending/favorable/unfavorable/interim clearance granted, final clearance level)

### Onboarding Checklist

- **Onboarding workflow system** — task list (task ID, task name, category: HR/IT/Facilities/Security/Training, owner, assigned to, due date, status: not started/in progress/completed/blocked, completion date, completion evidence), overall onboarding progress score, milestone events (offer accepted, start date confirmed, day-1 check-in, 30/60/90-day check-in dates)

### Access Provisioning

- **Access provisioning tracker** — provisioning requests (request ID, employee, system name, access type, request date, approver, approval date, provisioning status: pending/approved/provisioned/denied, provisioning date, access expiration date if temporary)

### Policy Acknowledgments

- **Acknowledgment log** — acknowledgments (employee ID, policy document title, document version, date presented, date signed, method: electronic/wet signature, witness if applicable, filing location in HRIS)
