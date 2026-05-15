# Tools Reference — Documentation Agent

## Ambient Clinical Documentation
- **Nuance DAX (Dragon Ambient eXperience)** — AI ambient scribe; converts clinical encounter conversation into structured note draft (SOAP, H&P, progress note); REST API with facility credentials; note content written to EHR draft after clinician review
- **Abridge** — real-time ambient note generation from encounter audio; specialty-specific note templates; REST API with subscription
- **Suki AI** — voice-driven clinical documentation; AI note suggestions integrated into EHR workflow; REST API

## EHR Documentation APIs
- **Epic FHIR R4 / Epic Hyperdrive API** — read existing notes (DocumentReference), read encounter context (Encounter, Condition, Observation, MedicationRequest), write draft notes to In-Basket for clinician review; SmartText and SmartPhrase template retrieval
- **Cerner Millennium PowerChart API** — read existing documentation, create note drafts in Cerner workflow; FHIR DocumentReference write scopes

## CDI & Quality Review
- **3M 360 Encompass CDI Module** — documentation gap identification (missing specificity, MCC/CC opportunities, CC capture rate), physician query workflow, CDI query templates, response tracking; REST API with facility credentials
- **Nuance Clintegrity CDI** — concurrent CDI workflow, query management, documentation quality scoring, case complexity analysis; REST API

## Template Management
- **Epic SmartPhrase / SmartText Library** — institutional note templates, quick text expansions, dot phrases for common documentation elements; read via Epic API
- **Cerner PowerNote Templates** — Cerner-native documentation templates by specialty and note type; read via Cerner API

## Data Sources

### Clinical Note Content (read, minimum necessary)

- **Epic / Cerner FHIR R4 DocumentReference** — note type (LOINC document type code), note author NPI, authored date, encounter ID, note status (preliminary/final/amended), document content (text, structured sections: Chief Complaint, HPI, ROS, Exam, Assessment, Plan), co-signature status, co-signer NPI

### Encounter Context (read-only)

- **Epic / Cerner FHIR R4**
  - `Encounter`: encounter class, service type, admission date, discharge date, attending NPI, resident NPI, encounter status
  - `Condition`: active diagnoses (ICD-10-CM, SNOMED CT), clinical status, POA indicator
  - `Observation` (vitals and labs): LOINC code, value, unit, interpretation, effective date/time
  - `MedicationRequest`: active medications with dose, route, frequency for medication reconciliation context

### CDI / Documentation Quality Metrics

- **3M 360 Encompass / Nuance Clintegrity**
  - CDI query: query ID, account/encounter ID, query type (clarification/leading/multiple choice), query text, queried physician NPI, date sent, response status (pending/answered/expired), response content, impact on DRG (before/after), CC/MCC capture flag
  - Documentation quality scores: specificity score, completeness score, query rate, agreement rate, CC capture rate, case mix index (CMI) by service and physician

### Note Templates & SmartPhrases

- **Epic SmartPhrase Library** — phrase name, phrase category, specialty, text content, variable slots, author, last modified date
- **Cerner PowerNote Template Library** — template name, template type, specialty, section structure, default text, version
