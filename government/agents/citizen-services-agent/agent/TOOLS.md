Available integrations for citizen services:

- **Accela / Tyler EnerGov / OpenGov** — permit lookup, permit application submission, inspection scheduling, fee calculation, and status tracking for building, land use, business license, and environmental permits
- **Salesforce Government Cloud / Dynamics 365** — case management: create, read, update citizen service cases; attach notes; trigger case worker assignment workflows
- **Benefits eligibility engine** — query program eligibility rules (income thresholds, residency requirements, documentation checklist) for benefits programs; returns eligibility criteria and application links, not determinations
- **Payment gateway (Pay.gov / Stripe)** — retrieve fee schedules, generate payment references, confirm payment receipt for permit and service fees
- **Document repository** — retrieve approved form templates, instructions, and agency brochures in accessible formats (PDF, plain-text)
- **Queue / appointment scheduler** — check service center availability and book, reschedule, or cancel constituent appointments

## Data Sources

Systems and platforms commonly accessed for citizen service delivery.

### Permitting & Licensing

- **Accela Civic Platform** — permit records (permit number, type: building/electrical/plumbing/mechanical/fire, status: submitted/under review/approved/issued/closed/expired, parcel number, project address, applicant name, application date, issue date, expiration date, fee amount, fee status, assigned reviewer, inspection records: inspection type, scheduled date, result: pass/fail/partial, inspector name, correction notices)
- **Tyler EnerGov** — land-use applications (case number, case type: rezoning/variance/CUP/subdivision, status, project name, location, applicant, hearing date, board decision, conditions of approval), business licenses (license number, business name, DBA, owner, address, license type, issue date, expiration date, renewal status, inspection history)
- **OpenGov Permitting & Licensing** — online applications (application ID, form type, submission date, attachments, review queue position, reviewer comments, applicant contact), fee schedule (fee code, description, calculation method, amount), public portal activity (views, applications started, applications submitted)

### Case Management

- **Salesforce Government Cloud** — service cases (case ID, subject, description, status: new/in progress/escalated/resolved/closed, priority, category, constituent contact, created date, last updated, case owner, case team, resolution summary, satisfaction score), knowledge articles linked to case, email/phone log, SLA compliance (response SLA, resolution SLA, breach flag)
- **Microsoft Dynamics 365 Government** — citizen records (contact ID, name, address, phone, email, preferred language, case history, document attachments), service requests (request ID, service type, channel: web/phone/in-person/chat, status, assigned worker, expected completion date, notes)

### Benefits Administration

- **Eligibility rules engine** — program catalog (program name, administering agency, eligibility criteria: income limits by household size, residency requirement, citizenship/immigration status requirement, age/disability criteria), required documentation checklist, application portal URL, processing time SLA, appeal process description

### Payments

- **Pay.gov** — payment records (payment reference number, amount, fee code, status: pending/completed/failed/refunded, payment method, timestamp, confirmation number)
- **Agency fee schedule** — fee code, service type, base fee, additional unit cost, waiver criteria
