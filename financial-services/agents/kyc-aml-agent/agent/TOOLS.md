# Tools Reference — KYC/AML Specialist

## Sanctions and Watchlist Screening

- **LexisNexis WorldCompliance** — screen individuals and entities against OFAC SDN, consolidated non-SDN lists, FATF grey/black lists, PEP databases, and adverse media; retrieve screening results with confidence scores and match detail; log list version used at time of screening
- **Dow Jones Risk & Compliance** — access PEP and sanctions screening, adverse media search, and state-owned enterprise data; retrieve enhanced due diligence profiles for high-risk customers
- **Refinitiv World-Check One** — screen against global sanctions, regulatory, law enforcement, and PEP lists; access risk intelligence profiles; pull ongoing monitoring alerts for existing customers
- **OFAC SDN Direct API** — query the current OFAC SDN and consolidated lists directly; confirm list version and effective date for each screening run

## Identity Verification

- **Jumio** — submit document capture and biometric verification requests for individual KYC; retrieve verification outcomes, extracted data, and liveness check results
- **Onfido** — access document authenticity checks, facial comparison, and database validation; retrieve report results and risk signals
- **Acuant** — verify government-issued ID documents; retrieve data extraction results and fraud indicator flags

## AML Transaction Monitoring

- **NICE Actimize SAM** — retrieve transaction monitoring alerts; access alert queue, transaction detail, and customer profile context; update alert disposition and investigation notes; route SAR-eligible cases to the BSA Officer
- **Oracle Financial Services AML** — query alert workbench, pull scenario-triggered alerts, retrieve scenario parameters and typology descriptions; access case management workflow
- **Tonbeller / Siron AML** — access watchlist management, transaction scenario monitoring, and case management; retrieve risk score outputs and alert narratives

## Customer Data

- **Core Banking / Account System** — retrieve customer account records, transaction history, product holdings, and relationship data for CDD and EDD reviews
- **FinCEN Beneficial Ownership Registry** — query for entity ownership data submitted under the CTA (Corporate Transparency Act) to support CDD legal entity verification

## Data Sources

### Customer Identity and CDD

- **Core Banking / Account System** — customer profile (customer ID, legal name, date of birth, SSN/TIN/EIN, citizenship, address, account types, open date, account status, relationship manager), account activity (account number, transaction history, average balances, product holdings, linked accounts, beneficiaries)
- **CDD/EDD Records** — customer due diligence (customer ID, CDD tier, CDD completion date, risk rating, review cycle, next review date, EDD trigger flag, EDD completion date, EDD analyst, EDD findings summary)
- **Beneficial Ownership Records** — (entity customer ID, legal name, TIN/EIN, jurisdiction of formation, beneficial owners — name, DOB, address, SSN, ownership percentage, controlling person flag, certification date, certifying officer)

### Sanctions and Screening

- **LexisNexis WorldCompliance** — screening results (screening ID, customer ID, search name, search date, list name, list version, match type, match confidence score, matched name, matched DOB, matched nationality, match detail, disposition — true match/false positive, analyst ID, disposition date, notes)
- **OFAC SDN List** — direct query results (query name, DOB, nationality, list date, SDN entry, program, aliases, addresses, additional remarks, query timestamp, list version)
- **PEP Database** — PEP screening (customer ID, matched name, PEP category, country, position, jurisdiction, appointment date, related parties, risk level, disposition)

### AML Transaction Monitoring

- **NICE Actimize SAM** — alert records (alert ID, customer ID, account, alert date, scenario ID, scenario name, typology, risk score, transaction amount, currency, counterparty, alert status, analyst, disposition, SAR referral flag, close reason, investigation notes)
- **Oracle FCCM** — case records (case ID, alert IDs included, customer, account, case type, opened date, assigned analyst, investigation status, findings, SAR recommendation, supervisor review, closure date)

### Regulatory

- **FinCEN Beneficial Ownership Registry** — CTA filing records (reporting company name, EIN, jurisdiction, filing date, beneficial owner data, exempt status, filing status)
- **AML Audit Log** — (event type — screening run/CDD completed/alert dispositioned/SAR referred/case closed, customer ID, analyst ID, timestamp, list version used, outcome, regulatory reference)
