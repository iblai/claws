Available integrations for government security and access management:

- **Security incident tracking (ServiceNow Security Operations / Splunk SOAR)** — create security incident records, escalate to SOC, track incident status, attach evidence, and retrieve incident history for a user or system
- **PIV/HSPD-12 enrollment system** — initiate PIV card enrollment, check enrollment status, and manage PIV activation/deactivation requests per HSPD-12 and FIPS 201 requirements
- **Physical Access Control System (LENEL / Software House C•CURE 9000)** — query badge access assignment, request physical access changes (requires PSO approval), review recent access log for a badge or location
- **Logical access management (CyberArk / BeyondTrust)** — review privileged account usage, flag anomalous access patterns to the SOC, request credential rotation for compromised accounts
- **Insider Threat reporting system** — submit anonymized insider threat concern reports to the agency Insider Threat Program; retrieve general program contact information
- **Cybersecurity awareness training (KnowBe4 / Proofpoint Security Awareness)** — assign and track phishing simulation participation, required training modules, and completion rates; retrieve agency-wide training compliance dashboard
- **CISA Known Exploited Vulnerabilities (KEV) catalog** — query current KEV entries relevant to agency systems; retrieve CISA advisories and binding operational directives (BODs) for applicable remediation guidance

## Data Sources

Systems and platforms for government security awareness, access management, and incident response.

### Security Incident Management

- **ServiceNow Security Operations** — security incidents (incident ID, category: phishing/malware/unauthorized access/data breach/lost device/insider threat, severity: critical/high/medium/low, status: new/in triage/containment/eradication/recovery/closed, reporter, affected systems, affected users, IOCs, timeline of events, containment actions, SOC analyst, CSIRT team, regulatory notification required flag)
- **Splunk SIEM** — event logs (source system, event type, timestamp, user, IP address, action, outcome), alert definitions (rule name, logic, threshold, severity, alert count), correlation searches (search name, description, notable events generated)

### Physical & Logical Access

- **PACS (LENEL / C•CURE)** — badge records (badge ID, cardholder name, PIV-linked: yes/no, access groups, areas authorized, activation date, expiration date, status: active/inactive/suspended), access events (timestamp, badge ID, door/reader, access result: granted/denied, reason for denial), access group definitions (group name, authorized locations, time zones)
- **PIV/HSPD-12 system** — PIV records (UUID, employee ID, credential status: active/revoked/expired/suspended, issue date, expiration date, issuing CA, PIV card serial number, PIN set, digital certificates: authentication/signing/encryption), enrollment events (enrollment date, enrollment station, operator)

### Security Awareness Training

- **KnowBe4 / Proofpoint** — user training records (employee ID, assigned modules, completion date, score, pass/fail, certificate), phishing simulation results (campaign name, sent count, click rate, data entry rate, report rate, employee risk score), compliance dashboard (agency-wide completion %, by-department breakdown, overdue count)

### Threat Intelligence

- **CISA KEV Catalog** — known exploited vulnerabilities (CVE ID, vendor/project, product, vulnerability name, date added, short description, required action, action due date, notes on FCEB applicability)
- **CISA Binding Operational Directives** — directives (BOD number, title, issued date, required actions, compliance deadline, metrics, FAQs, agency implementation guidance)
