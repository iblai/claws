# Tools Reference — Provider Onboarding Agent

## Credentialing Platforms
- **symplr Credentialing (formerly Morrisey)** — end-to-end credentialing workflow; provider file management, privilege tracking, reappointment scheduling, committee action tracking; REST API with facility credentials
- **MD-Staff (NurseGrid / symplr)** — medical staff office platform for credentialing, privileging, and appointment; expiration tracking, reporting; REST API
- **Verity (Modio Health)** — provider credentialing and enrollment SaaS; document management, primary source verification queue, payer enrollment tracking; REST API

## Primary Source Verification
- **NPPES NPI Registry (CMS)** — NPI number, provider name, taxonomy (specialty), address, phone, license numbers; public REST API
- **CAQH ProView** — provider-submitted credentials, attestation date, authorization to release; CAQH Organization ID lookup via REST API with payer/health system credentials
- **ABMS BoardVitals / AMA Physician Profiles** — board certification (specialty, sub-specialty, certification date, expiration); API with institutional license
- **DEA Diversion Control Division** — DEA registration verification (registration number, schedules, expiration date, registrant name, business activity); public lookup endpoint

## Payer Enrollment
- **Availity Essentials** — payer enrollment status by provider and payer, enrollment transaction submission, roster management; REST API with clearinghouse credentials
- **Provider Enrollment, Chain and Ownership System (PECOS)** — CMS Medicare enrollment status, reassignment records, enrollment type; public lookup API

## HRIS / Onboarding
- **Workday HCM** — new hire record (name, NPI, department, start date, job title, supervisor); used to trigger orientation checklists; read-only REST API
- **HealthStream / Relias LMS** — orientation curriculum assignment triggered on hire; completion status tracking

## Data Sources

### Credentialing System Data

- **symplr / MD-Staff** — provider ID, full name, NPI (type 1), specialty (primary, secondary), department, provider type (MD/DO/NP/PA/etc.), application status (initial/reappointment/expedited), privileges requested (privilege name, category, requirements met), privileges granted (with effective and expiration dates), committee review dates, current appointment status, reappointment due date, license expiration alerts

### Primary Source Verification Results

- **NPPES** — NPI, provider name, credential (MD/DO/NP/PA), taxonomy code/description, license state and number, practice address, phone, enumeration date, deactivation status
- **CAQH ProView** — attestation date, authorization expiration, specialty, hospital affiliations, malpractice coverage (carrier, limits, effective/expiration), sanctions and disciplinary actions (yes/no per category), gap in coverage explanation
- **ABMS** — board name, specialty, sub-specialty, initial certification date, most recent certification date, expiration date, certification status (certified/not certified/closed)
- **DEA** — DEA registration number, schedules (II, III, IV, V), registration status (active/expired/revoked), expiration date, state, business activity type

### Payer Enrollment Data

- **Availity / PECOS** — payer name, payer ID, enrollment status (enrolled/pending/not enrolled/terminated), application submission date, effective date, provider type, NPI, TIN, billing address

### Onboarding Checklist

- **Workday / LMS integration** — checklist item name, category (compliance training, orientation module, credentialing document, IT access), assigned date, due date, completion date, completion status, responsible party
