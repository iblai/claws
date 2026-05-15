# Tools Reference — Research Agent

## Biomedical Literature Databases
- **PubMed / MEDLINE (NCBI E-utilities)** — Entrez API for structured literature search (MeSH terms, free text, PICO filters, date ranges, publication type filters); abstract retrieval, citation export (PMID, DOI); public API with institutional API key for rate limit increase
- **Cochrane Library** — systematic reviews, meta-analyses, and Cochrane protocols; structured search API with institutional subscription credentials
- **Embase (Elsevier)** — broader biomedical and pharmacological literature; Embase REST API with institutional license; strong for drug and device trials
- **Semantic Scholar** — open scholarly literature search with citation graph, influence scores, and open-access PDF links; public API

## Clinical Trial Registries
- **ClinicalTrials.gov API (v2)** — full trial record (NCT ID, title, sponsor, phase, status, condition, intervention, eligibility criteria, locations, primary/secondary outcomes, enrollment target, start/completion dates); free public API
- **WHO International Clinical Trials Registry Platform (ICTRP)** — cross-registry trial search for non-US trials; public REST feed

## Evidence Synthesis Tools
- **Covidence (Veritas Health Innovation)** — systematic review workflow management; title/abstract screening, full-text review, data extraction templates; API with institutional subscription
- **DistillerSR** — systematic review screening and extraction; REST API with subscription credentials

## Institutional Repository
- **Institutional Research Repository** — institutional preprints, internal study reports, IRB-approved protocol documents; on-premises REST API with service account

## Data Sources

### Literature Databases

- **PubMed / MEDLINE** — PMID, article title, authors (last name, initials), journal (full name, ISO abbreviation), year, volume, issue, pages, DOI, MeSH terms, abstract text, publication type (RCT, meta-analysis, review, case report, etc.), funding sources, conflict of interest statement, open-access status
- **Cochrane Library** — review ID, title, authors, Cochrane group, publication date, type (systematic review, protocol, overview), PICO elements (population, intervention, comparison, outcomes), GRADE evidence quality ratings, key findings summary, DOI
- **Embase** — Embase accession number, title, authors, journal, year, Emtree terms (drug name, disease name, device), subheadings, conference abstract flag, ahead-of-print flag, DOI

### Clinical Trial Data

- **ClinicalTrials.gov** — NCT ID, brief title, official title, sponsor (name, type), collaborators, status (recruiting/active/completed/terminated), phase (1/2/3/4), study type (interventional/observational), condition (MeSH), intervention (name, type, description), eligibility (inclusion criteria, exclusion criteria, minimum age, maximum age, sex, healthy volunteers), primary outcome measure, secondary outcome measures, enrollment target, start date, primary completion date, study sites (facility name, city, state, country, status), results available flag

### Evidence Quality Metadata

- **GRADE framework fields** — certainty of evidence (high/moderate/low/very low), risk of bias assessment, inconsistency rating, indirectness rating, imprecision rating, publication bias assessment, upgrading factors
- **JADAD / Cochrane RoB 2.0 fields** — randomization adequacy, allocation concealment, blinding (participants, personnel, outcome assessors), incomplete outcome data, selective reporting, other bias sources
