# Tools Reference — Onboarding Specialist

## Account Opening and Document Collection

- **DocuSign** — send and track electronic signature requests for new account agreements, advisory agreements, Form CRS, and other required disclosures; retrieve signed document status and completion audit trail
- **Laserfiche** — store and index onboarding documents; retrieve document checklist completeness by account; trigger document expiry reminders for annual FATCA re-certification
- **Salesforce Financial Services Cloud** — create and update client household and account records; track onboarding workflow stage; log suitability assessment results and document delivery confirmations

## Custodian Account Opening

- **Schwab Advisor Center API** — submit new account opening packets; retrieve account number assignment and approval status; pull account type forms and custodian-specific requirements
- **Fidelity WealthScape** — initiate account opening workflows; retrieve document requirements by account type; access custodian form library for individual, joint, trust, and retirement accounts
- **Pershing NetX360** — submit account applications; retrieve NIGO (Not In Good Order) notifications; pull custodian form status and pending items list

## Suitability and Financial Planning

- **Riskalyze / Nitrogen** — administer risk tolerance questionnaire; retrieve client Risk Number; compare proposed allocation to stated risk tolerance; generate Risk Analysis Report for advisor review and file
- **MoneyGuidePro** — retrieve existing financial plan goals and assumptions; run quick cash flow analysis for suitability context; pull retirement readiness score for client profile

## Regulatory Forms and Certifications

- **W-9 / W-8 Validation Tool** — validate FATCA certifications (W-9, W-8BEN, W-8BEN-E, W-8IMY) for accuracy and completeness; flag indicia of foreign status; trigger enhanced FATCA review workflow
- **Form CRS Delivery Tracker** — confirm Form CRS delivery timestamp and client acknowledgment; log delivery method and proof of receipt for examination readiness

## Data Sources

### Client Profile and Documents

- **Salesforce Financial Services Cloud** — client record (client ID, household ID, first name, last name, date of birth, SSN/TIN, citizenship, contact info, address, employment, income, net worth, liquid assets, relationship manager, segment, referral source), account request (account type, custodian, investment objective, initial funding amount, date submitted, stage, outstanding items list)
- **Document Repository (Laserfiche / SharePoint)** — onboarding documents (document ID, type — new account agreement, advisory agreement, custodian application, Form CRS, privacy notice, W-9/W-8, suitability questionnaire, driver's license, proof of address, trust agreement, entity docs, status — collected/pending/expired, upload date, expiry date, reviewer)

### Custodian Account Opening

- **Schwab Advisor Center** — account application (application ID, client name, account type, custodian form set, submission date, status — in review/approved/NIGO, account number assigned, NIGO reason, outstanding items)
- **Fidelity WealthScape** — account opening records (application ID, account type, form completion status, NIGO flags, approval date, custodian account number)
- **Pershing NetX360** — account application (application ID, account type, submission date, status, NIGO items, account number, margin agreement status)

### Suitability

- **Riskalyze / Nitrogen** — suitability assessment (client ID, assessment date, questionnaire responses, Risk Number, portfolio alignment status, proposed allocation Risk Number, suitability outcome, advisor sign-off date)
- **MoneyGuidePro** — financial plan summary (plan ID, client ID, goals, total assets, liabilities, income, savings rate, retirement date, retirement readiness score)

### Regulatory Disclosures and Certifications

- **Form CRS Delivery Log** — (client ID, Form CRS version, delivery date, delivery method, acknowledgment date, acknowledgment method, advisor ID)
- **FATCA/CRS Certification Records** — (client ID, account number, form type — W-9/W-8BEN/W-8BEN-E/W-8IMY, certification date, expiry date, US indicia review status, foreign financial institution flag, GIIN if applicable, certifying name, recertification due date)

### Audit Trail

- **Onboarding Audit Log** — (event type — document received/verified/rejected/disclosure delivered/KYC cleared/account opened, client ID, account number, operator ID, timestamp, document reference, KYC clearance reference, supervisor approval if applicable)
