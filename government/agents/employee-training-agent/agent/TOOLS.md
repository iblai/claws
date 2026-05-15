Available integrations for government employee training:

- **Cornerstone OnDemand / SAP SuccessFactors Learning / Saba** — query employee transcript (completed courses, completion dates, scores, certificates); check mandatory training compliance status; browse course catalog; enroll employees in courses; trigger supervisor notifications for overdue mandatory training
- **OPM HR Connect / USA Learning (usda.gov/training)** — access federal training catalogs and mandatory course requirements by position series and grade; retrieve compliance requirements from OPM policy
- **CSRC NIST / CISA Training Portal** — retrieve cybersecurity awareness training content and completion requirements under FISMA and agency policy
- **Agency talent management system** — view employee individual development plans (IDPs), competency assessments, position training requirements, and certification tracking
- **Calendar / scheduler** — check employee availability and enroll in instructor-led training sessions; send calendar invitations for training sessions
- **Certification body verification** — verify external professional certification validity (e.g., FAC-C for acquisition, PMP, CISSP) via issuing body APIs

## Data Sources

Systems and platforms for government workforce training and development.

### Learning Management Systems

- **Cornerstone OnDemand (FedRAMP)** — transcripts (user ID, course ID, course title, completion date, score, pass/fail, certificate URL, credit hours, CEU credits, training type: mandatory/elective/developmental), enrollment records (enrollment ID, user, course, status: enrolled/in-progress/completed/withdrawn, due date, supervisor-assigned flag), curriculum assignments (curriculum name, assigned population, required courses, target completion date, completion rate), compliance reporting (compliance period, requirement met: yes/no/partial, overdue count, completion rate by org unit)
- **SAP SuccessFactors Learning** — learning items (item ID, title, delivery method: online/instructor-led/blended, duration, vendor, revision date), completion history (item ID, user, completion date, status, score, attempts), compliance requirements (rule name, subject population, required items, completion window, escalation schedule)

### Federal Training Catalogs

- **USA Learning** — course listings (course number, title, offering agency, audience, credit hours, cost, schedule, delivery type), mandatory requirements by series (OPM occupational series, required courses, frequency, deadline rule)
- **OPM Policy Directives** — training requirements (regulatory citation, position category, training topic, frequency: annual/biennial/one-time, completion evidence accepted)

### Talent & Development

- **Agency IDP system** — individual development plans (employee ID, plan year, development goals, planned activities, supervisor approval status, progress notes, completion percentage), competency assessments (competency name, proficiency level required, current level, gap, recommended learning), position training requirements (position number, series, grade, required competencies, mandatory training checklist)

### Certifications

- **External certification records** — certification type, issuing body, employee name, certification number, issue date, expiration date, CPE/CEU maintenance requirements, renewal status
