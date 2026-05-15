# Tools Reference — Medical Coding Agent

## Computer-Assisted Coding (CAC) & Encoder Platforms
- **Optum360 EncoderPro / Optum CAC** — ICD-10-CM/PCS and CPT/HCPCS encoder with Official Guidelines, AHA Coding Clinic references, DRG grouper (MS-DRG, APR-DRG); REST API
- **3M 360 Encompass (Solventum)** — CAC, CDI, and coding workflow; DRG and APC assignment; charge capture integration; REST API with facility credentials
- **Nuance Clintegrity (Microsoft)** — NLP-assisted code suggestion from clinical notes, CDI query management, coding quality dashboards; REST API

## Coding References
- **CMS ICD-10-CM/PCS Tabular and Index** — public data files from cms.gov; refreshed annually (October 1 effective date)
- **AMA CPT Code Set** — licensed CPT code descriptor lookup and parenthetical note retrieval via Optum360 integration
- **AHA Coding Clinic** — official ICD-10-CM/PCS coding guidance; accessed via Optum360 EncoderPro API

## Claim Scrubbing & Edits
- **Change Healthcare ClaimScrubber / Optum iEDI** — NCCI edits, MUE edits, LCD/NCD coverage logic, payer-specific edits; REST API with clearinghouse credentials
- **Waystar (formerly ZirMed)** — real-time claim edit checking, eligibility integration, denial reason lookups; REST API

## EHR Documentation (read-only)
- **Epic FHIR R4** — encounter notes (DocumentReference), discharge summary, problem list (Condition), procedure records (Procedure), diagnosis codes already in chart
- **Cerner Millennium FHIR R4** — same resource types for Cerner deployments

## Data Sources

### ICD-10 & CPT Reference Data

- **CMS ICD-10-CM Tabular / Index** — code (full), descriptor (short and full), valid/invalid flag, effective date, code type (diagnosis, external cause, Z-code), specificity level, inclusion/exclusion notes, code-first and use-additional instructions
- **CMS ICD-10-PCS Tables** — section, body system, root operation, body part, approach, device, qualifier; valid code construction validation
- **AMA CPT Code Set (via Optum360)** — CPT code, short descriptor, long descriptor, category (I/II/III), parenthetical notes, CMS RVU (work, practice expense, malpractice), global days, modifier applicability

### DRG Grouping

- **3M / CMS MS-DRG Grouper** — principal diagnosis, secondary diagnoses (MCC/CC flags, POA status), procedure codes, patient age, discharge status → MS-DRG, relative weight, geometric mean LOS, arithmetic mean LOS
- **APR-DRG (3M)** — same inputs → APR-DRG, severity of illness level (1-4), risk of mortality level (1-4), relative weight

### Claim Edit Databases

- **NCCI (National Correct Coding Initiative)** — code pair (column 1, column 2), edit type (procedure-to-procedure, medically unlikely), modifier indicator (modifier allowed / not allowed), effective date, deletion date
- **CMS MUE Table** — HCPCS/CPT code, MUE value, adjudication indicator (claim/line/date of service)

### EHR Encounter Data (read-only, minimum necessary)

- **Epic / Cerner FHIR R4**
  - `DocumentReference`: document type, creation date, author NPI, attachment (base64 clinical note text)
  - `Condition`: ICD-10 code, POA indicator, clinical status, verification status
  - `Procedure`: CPT/SNOMED code, performed date, performing provider NPI, status
  - `Encounter`: encounter class, admit/discharge dates, discharge disposition, attending physician NPI
