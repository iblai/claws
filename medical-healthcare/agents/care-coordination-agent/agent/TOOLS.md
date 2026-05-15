# Tools Reference — Care Coordination Agent

## EHR Care Management Modules
- **Epic Care Everywhere / Referral Management** — create and track referral orders (ServiceRequest), view referral status, receive specialist notes back into the chart; FHIR R4 API with write scopes for ServiceRequest
- **Cerner Power Chart Care Management** — referral order management, transition of care documentation, care plan updates; FHIR R4 API

## Provider Scheduling Platforms
- **Kyruus ProviderMatch** — specialist directory with specialty, location, insurance acceptance, next available appointment; REST API with health system credentials
- **Nuance Precision Scheduling** — intelligent appointment slot matching based on referral urgency and patient need; REST API
- **Epic MyChart Scheduling API** — direct patient appointment booking within Epic network; SMART on FHIR scheduling workflow

## Care Management Platforms
- **Innovaccer** — unified patient data, care gap identification, risk stratification (low/medium/high/rising risk), care plan management, SDOH screening integration; REST API with facility credentials
- **Health Edge (Milliman) / Jiva** — care management platform for complex case management, utilization management, transition of care workflow; REST API

## Transitions of Care
- **Apixio / Manifest MedEx** — longitudinal patient record aggregation across care settings; transitions of care event detection (hospital admit, discharge, ED visit); REST API
- **CommonWell Health Alliance / Carequality network** — cross-organization FHIR record exchange for transition of care summaries (CCD/C-CDA documents); FHIR R4 API

## Community Resources
- **NowPow / Findhelp (Aunt Bertha)** — SDOH resource directory (food, housing, transportation, behavioral health); closed-loop referral to community-based organizations; REST API

## Data Sources

### Referral & Care Transition Data

- **Epic / Cerner FHIR R4**
  - `ServiceRequest` (referral): referral ID, ordering provider NPI, referred-to specialty/provider, urgency (routine/urgent/ASAP), reason code (ICD-10), status (draft/active/completed/revoked), authored date, note text
  - `Appointment`: appointment ID, participant (patient, practitioner), service type, specialty, start/end time, status (booked/fulfilled/cancelled/no-show), cancellation reason
  - `CarePlan`: care plan ID, category, goal(s), activity (scheduled/completed/cancelled), author, period, care team members
  - `CommunicationRequest`: outreach task, recipient (patient/caregiver), payload (message content), occurrence (scheduled date/time), requester, status

### Risk Stratification & Care Gaps

- **Innovaccer / Health Edge** — patient risk score (0-100), risk tier, risk drivers (diagnosis codes, utilization events, SDOH flags), care gaps (gap name, measure, last service date, target service date), care manager assigned, care plan status, last outreach attempt (date, modality, outcome)

### Transitions of Care Events

- **Apixio / Manifest MedEx** — event type (inpatient admit, inpatient discharge, ED visit, SNF admit, SNF discharge, home health start), facility name, admission date, discharge date, discharge disposition (home, SNF, rehab, hospice, AMA), discharge diagnosis codes (ICD-10), attending provider NPI, discharge summary available (yes/no)

### Community Resource Referrals

- **Findhelp (Aunt Bertha) / NowPow** — resource category (food/housing/transportation/financial/behavioral health/childcare), organization name, program name, referral status (sent/accepted/attended/closed), referral date, closure reason, CBO (community-based organization) contact
