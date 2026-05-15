# Tools Reference — Clinical Support Agent

## Clinical Decision Support
- **UpToDate (Wolters Kluwer)** — topic-based clinical summaries, treatment recommendations, drug monographs; accessed via REST API with institutional license key
- **Micromedex (IBM/Merative)** — drug interactions, dosing, toxicology, IV compatibility; REST API with facility credentials
- **ClinicalKey (Elsevier)** — full-text clinical references, First Consult summaries, clinical guidelines; API with institutional subscription

## Drug Reference & Interaction Checking
- **FDB (First Databank)** — drug-drug, drug-allergy, drug-disease interaction screening; dose range checking; REST API
- **Wolters Kluwer Medi-Span** — formulary data, drug monographs, interaction alerts; REST API

## EHR Integration (read-only)
- **Epic FHIR R4** — active medications (MedicationRequest), allergy list (AllergyIntolerance), problem list (Condition), recent lab results (Observation); read-only for context
- **Cerner Millennium FHIR R4** — same resource types for Cerner deployments

## Clinical Guidelines
- **AHA/ACC, IDSA, ACOG, AAP guidelines** — accessed via UpToDate and ClinicalKey integrations above
- **CDC clinical guidelines** — public REST endpoints (guidelines.gov, cdc.gov/api); no auth required

## Calculators
- **MDCalc API** — validated clinical scoring tools (CURB-65, Wells Criteria, CHADS2-VASc, Sepsis-3, NIH Stroke Scale, APACHE II); REST API

## Data Sources

### Clinical Reference Platforms

- **UpToDate** — topic titles, last review dates, recommendation grades (A/B/C), evidence levels (1/2/3), author/editor attribution, referenced guidelines (name, issuing body, year), related topics links
- **Micromedex** — drug generic name, brand names, drug class, indications, contraindications, dosing (adult/pediatric/renal/hepatic adjusted), route, frequency, interaction severity (contraindicated/major/moderate/minor), interaction mechanism, interaction clinical effect, allergy cross-reactivity data
- **FDB MedKnowledge** — drug identifier (NDC, RxNorm), interaction pair (drug A, drug B), interaction severity level, interaction description, management recommendation, onset/duration, documentation quality rating

### EHR Patient Context (read-only, minimum necessary)

- **Epic / Cerner FHIR R4**
  - `MedicationRequest`: medication code (RxNorm), dose, route, frequency, status, authored date
  - `AllergyIntolerance`: substance (code, display), reaction (manifestation, severity), clinical status, verification status
  - `Condition`: problem code (ICD-10-CM, SNOMED CT), clinical status, onset date
  - `Observation` (labs): code (LOINC), value, unit, reference range, interpretation (H/L/critical), effective date/time

### Clinical Scoring & Decision Tools

- **MDCalc** — calculator name, input parameters (with units and reference ranges), output score, score interpretation (risk category, recommended action), evidence citations

### Institutional Protocols (on-premises)

- **Institutional Protocol Repository** — protocol title, version, effective date, owning department, clinical area, applicable diagnoses (ICD-10), procedure steps, order set links, last review date, approving committee
