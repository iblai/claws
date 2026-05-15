# Tools Reference — Prior Authorization Agent

## Clearinghouse & Eligibility Platforms
- **Availity Essentials** — real-time eligibility (270/271 X12), PA initiation and status (278 X12), remittance advice, payer-specific PA requirement lookup; REST API with facility credentials
- **Waystar (formerly ZirMed/Navicure)** — eligibility verification, prior authorization workflow, denial management, claim status; REST API
- **Change Healthcare (Optum)** — eligibility, PA transactions, real-time benefit checking, clinical attachment submission; REST API

## PA-Specific Clinical Decision Support
- **MCG Health (Milliman Care Guidelines)** — evidence-based clinical criteria for PA decisions; procedure-level criteria lookup (inpatient, outpatient, home health, SNF); API with licensing credentials
- **InterQual (Optum/Change Healthcare)** — care criteria for PA and utilization management; inpatient/surgical/behavioral health criteria sets; API with license

## EHR Integration (read-only)
- **Epic FHIR R4** — coverage/insurance (Coverage resource), active diagnoses (Condition), ordered procedures (ServiceRequest/Procedure), ordering provider NPI (Practitioner), encounter details (Encounter)
- **Cerner Millennium FHIR R4** — same resource types for Cerner deployments

## Payer Coverage Policy Databases
- **Payer LCD/NCD policies (CMS)** — Local Coverage Determinations and National Coverage Determinations; public CMS API for Medicare policies
- **Payer-specific online portals** — payer clinical coverage policies and PA requirement PDFs retrieved via authenticated portal sessions

## Appeal Support
- **Clinical evidence databases (via research-agent)** — PubMed literature and UpToDate summaries surfaced to support medical necessity appeal letters

## Data Sources

### Eligibility & Benefits Data

- **Availity / Waystar (X12 270/271)** — payer name, payer ID, member ID, group number, plan name, coverage effective date, termination date, deductible (individual/family, met/remaining), out-of-pocket maximum (met/remaining), copay/coinsurance by service type, PA required (yes/no by service/CPT), in-network vs. out-of-network status, coordination of benefits flag

### Prior Authorization Records

- **Clearinghouse PA transactions (X12 278)** — authorization number, status (approved/denied/pending/modified), service type, requested CPT/HCPCS codes, approved units, approved dates (start/end), denial reason code (X12 AAA/CA segments), payer reviewer name/extension, submission timestamp, response timestamp, clinical attachment required flag

### Clinical Coverage Criteria

- **MCG Health / InterQual** — guideline name, version, indication, site of care (inpatient/outpatient/ED), clinical criteria (required diagnoses, severity indicators, prior treatments required, documentation requirements), approval recommendation (meets criteria/does not meet criteria), page/section reference

### EHR Patient & Order Context (read-only, minimum necessary)

- **Epic / Cerner FHIR R4**
  - `Coverage`: payer name, member ID, group number, subscriber relationship, coverage period
  - `ServiceRequest`: requested procedure (CPT/SNOMED), ordering provider NPI, priority (routine/urgent/ASAP/STAT), supporting information references
  - `Condition`: diagnosis codes (ICD-10-CM) supporting medical necessity
  - `DocumentReference`: clinical notes referenced in PA submission

### Denial & Appeal Tracking

- **Internal PA tracker (workspace)** — authorization ID, patient ID (tokenized), service type, payer, submission date, status, denial reason, appeal level, appeal submission date, appeal outcome, escalation flag
