# Tools Reference — Knowledge Management Agent

## Policy & Procedure Repositories
- **PolicyTech (NAVEX Global)** — healthcare policy and procedure management; document search by keyword, department, regulatory tag; version history, effective dates, attestation records; REST API with facility credentials
- **SharePoint (Microsoft 365)** — institutional document library for policies, procedures, clinical guidelines, forms; search via Microsoft Graph API with service account credentials
- **Confluence (Atlassian)** — departmental wikis and operational procedures (common in IT, quality, research departments); REST API with service account

## Clinical Protocol & Order Set Libraries
- **Epic Protocol Builder / Order Sets (Storyboard)** — institutional order sets and clinical pathways stored in Epic; retrieved via Epic FHIR R4 PlanDefinition resource; read-only access
- **Cerner Care Aware / Order Catalog** — Cerner order sets and care pathways; retrieved via Cerner FHIR PlanDefinition resources; read-only access
- **Zynx Health** — evidence-based order set content and clinical pathways with literature citations; REST API with institutional license

## Formulary & Drug Information
- **Micromedex / FDB (First Databank)** — institutional formulary status (formulary/non-formulary/restricted), therapeutic equivalents, formulary alternatives, PA required flag, restricted-use criteria; REST API with institutional license
- **Pharmacy Formulary Management System (e.g., Inmar, Macro Helix)** — institutional formulary database including tiered formulary status, quantity limits, step therapy requirements, prior authorization requirements; REST API

## Search Infrastructure
- **Elasticsearch (on-premises)** — full-text search index over institutional knowledge content (protocols, policies, FAQs, order sets); keyword and semantic search; relevance-ranked results with document metadata

## Data Sources

### Policy & Procedure Documents

- **PolicyTech / SharePoint** — document ID, document title, document type (policy/procedure/guideline/form/job aid), owning department, applicable roles/units, effective date, expiration/review date, version number, approval status (draft/approved/retired), approver name and title, regulatory cross-references (Joint Commission standard, CMS CoP, HIPAA CFR), full document body text, change summary (what changed from prior version)

### Clinical Protocols & Order Sets

- **Epic PlanDefinition (FHIR R4) / Zynx Health** — order set ID, order set name, clinical focus (diagnosis/procedure/condition), service line, last review date, approving committee, version, action items (order name, order type: medication/lab/imaging/nursing, default values, conditionals), related diagnoses (ICD-10-CM), CPT/procedure codes covered, evidence citations (guideline name, PMID)

### Formulary Data

- **Micromedex / FDB / Pharmacy Formulary System** — drug generic name, drug brand name(s), drug class (ATC code, therapeutic class), formulary tier (1/2/3/4/non-formulary), formulary status (preferred/non-preferred/restricted/non-formulary), restriction criteria (indication, prescriber specialty, prior authorization required), therapeutic alternative (generic name, tier, clinical equivalence note), formulary effective date, pharmacy benefit payer applicability

### Search Index Metadata

- **Elasticsearch** — document ID, title, content type, source system, relevance score, last indexed date, keyword matches, department, version, effective date; returned as ranked result list with excerpt snippets
