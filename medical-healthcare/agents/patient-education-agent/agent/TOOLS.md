# Tools Reference — Patient Education Agent

## Patient Education Content Libraries
- **Krames (StayWell / WebMD Health Services)** — condition education sheets, medication handouts, procedure prep instructions, discharge instruction templates; accessed via REST API with institutional license
- **Healthwise Knowledgebase** — clinician-authored patient education articles covering diagnoses, procedures, medications, and wellness topics; available in multiple languages; REST API
- **Elsevier Patient Education** — condition and medication handouts formatted for print and digital delivery; API with subscription credentials

## EHR Integration (read-only)
- **Epic MyChart FHIR R4** — active diagnoses (Condition), ordered medications (MedicationRequest), upcoming procedures (Procedure), and discharge planning notes to contextualize education content
- **Cerner Millennium FHIR R4** — same FHIR resource types for Cerner deployments

## Readability & Health Literacy
- **Flesch-Kincaid / SMOG grade calculator** — local utility invoked to score generated content; target score ≤ 6th grade unless clinician specifies otherwise
- **AHRQ Plain Language guidelines** — referenced checklist applied during content generation (active voice, short sentences, common words, teach-back cues)

## Translation Services
- **DeepL API / Azure Cognitive Services Translator** — machine translation of patient materials into target language; output marked as "machine translation — professional review recommended before clinical use"

## Document Output
- **Workspace file write** — saves draft materials to `/sandbox/.openclaw/workspace/` as `.txt` or `.html` for clinician review and approval before patient delivery

## Data Sources

### Patient Education Content Systems

- **Krames StayWell** — content ID, title, content type (condition, medication, procedure, discharge), language, reading level (grade), last review date, reviewing clinician/organization, format (HTML, PDF), condition ICD-10 tag, medication RxNorm tag
- **Healthwise Knowledgebase** — topic ID, title, summary, full content body, language code, reading grade level, last clinically reviewed date, linked conditions (SNOMED CT), linked medications (RxNorm), author credentials

### EHR Discharge & Encounter Context (read-only, minimum necessary)

- **Epic / Cerner FHIR R4**
  - `Condition`: problem code (ICD-10-CM, SNOMED CT), clinical status, onset date
  - `MedicationRequest`: medication name (RxNorm), dose, route, frequency, patient instructions field
  - `Procedure`: procedure code (CPT, SNOMED CT), status, performed date, body site
  - `CarePlan`: discharge instructions text, follow-up appointments, activity restrictions, diet instructions

### Readability Scoring

- **Flesch-Kincaid / SMOG** — raw text input, calculated grade level score, word count, sentence count, syllable count, recommended revisions

### Translation Metadata

- **DeepL / Azure Translator** — source language, target language, translation quality score, segments translated, machine translation flag (always true), recommended human review flag
