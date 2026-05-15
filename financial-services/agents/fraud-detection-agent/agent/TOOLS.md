# Tools Reference — Fraud Investigator

## Transaction Monitoring and Fraud Platforms

- **NICE Actimize Fraud** — retrieve real-time and batch fraud alerts; access alert queue sorted by risk score, account, and typology; pull transaction detail, device fingerprint, and behavioral analytics for alert review; update disposition and route SAR candidates to BSA Officer
- **Featurespace ARIC** — access adaptive behavioral analytics outputs; retrieve anomaly detection alerts; pull peer group deviation scores and entity risk profiles for investigation context
- **SAS Fraud Management** — retrieve fraud score outputs, rule-triggered alerts, and model feature explanations; access case investigation workbench; pull network link analysis results for connected account detection
- **Fiserv Financial Crime Risk Management** — access integrated fraud and AML alert queue; retrieve cross-channel transaction data; pull device, location, and authentication signal data for case analysis

## Case Management

- **ServiceNow** — create, update, and close fraud investigation cases; assign case owners and document investigation steps, interviews, and evidence; track SLA compliance and case aging
- **Internal Case Management System** — retrieve linked cases and prior fraud history for a customer or account; log investigation findings, disposition rationale, and SAR referral notes

## Supporting Data Sources

- **Core Banking / Account System** — retrieve full transaction history, account opening data, customer profile, linked accounts, and relationship data for fraud investigation
- **Card Network Disputes Platform (Visa/MC)** — access chargeback and dispute history; retrieve transaction authentication data and merchant detail for card fraud cases
- **Wire Transfer System** — pull wire instruction history, IP address metadata, and call-back verification records for wire fraud investigations
- **Cybersecurity / SIEM (Splunk)** — retrieve login event logs, failed authentication attempts, IP geolocation, and device change events correlated with suspicious transaction activity

## Data Sources

### Transaction Monitoring

- **NICE Actimize Fraud** — fraud alerts (alert ID, customer ID, account number, alert date, rule/model ID, fraud typology, risk score, flagged transaction ID, amount, currency, channel, counterparty, device ID, IP address, geolocation, alert status, analyst assigned, disposition, SAR referral flag, close reason)
- **Featurespace ARIC** — behavioral analytics (customer ID, event ID, ARIC risk score, peer group deviation, anomaly description, contributing features, event timeline, entity risk profile)
- **SAS Fraud Management** — model scores (transaction ID, score, rule triggers, feature values, score band, model version), network analysis (entity ID, linked accounts, transaction flow diagram, shared attributes — phone, email, address, device, IP)

### Core Transaction Data

- **Core Banking System** — transaction records (transaction ID, account number, date, time, channel, transaction type, amount, currency, counterparty account, merchant/beneficiary, description, status, reversal flag), account data (account number, customer ID, account type, open date, status, balance, average balance, transaction velocity)
- **Card Processing System** — card transactions (card number masked, merchant name, MCC, authorization amount, settlement amount, currency, country, authorization response code, device type, present/not-present flag, AVS/CVV result)
- **Wire Transfer System** — wire records (wire ID, originator, originator account, beneficiary, beneficiary bank, amount, currency, SWIFT message type, origination date, value date, purpose code, IP address at initiation, call-back verification status)

### Case Management

- **Fraud Case System** — investigation records (case ID, linked alert IDs, subject customer, accounts involved, case type, opened date, analyst, investigation steps, interviews conducted, evidence collected, typology classification, loss amount, recovery amount, SAR recommendation, supervisor review, closure date, disposition)
- **Prior Fraud History** — (customer ID, prior case IDs, case types, dates, outcomes, loss amounts, recovery, recurrence flag)

### Cybersecurity Correlation

- **Splunk SIEM** — authentication events (user, account, login timestamp, IP, geolocation, device, success/fail, MFA outcome, concurrent session flag), account change events (event type, user, changed field, timestamp, IP, requestor), anomaly alerts (alert ID, rule, severity, affected account, description)

### Audit Trail

- **Fraud Audit Log** — (event type — alert created/reviewed/escalated/closed/SAR referred, analyst ID, case ID, alert ID, timestamp, disposition rationale, evidence reference, supervisor sign-off)
