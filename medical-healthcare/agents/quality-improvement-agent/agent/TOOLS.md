# Tools Reference — Quality Improvement Agent

## Healthcare Analytics Platforms
- **Health Catalyst (Touchstone / ACE)** — clinical analytics platform with prebuilt HEDIS, readmission, mortality, and infection rate dashboards; measure performance trending, care gap patient lists, benchmarking; REST API with facility credentials
- **Innovaccer Analytics** — population health analytics, care gap identification, measure performance tracking, cohort analysis; REST API
- **Epic Cogito / SlicerDicer** — Epic-native analytics workbench for cohort analysis, measure performance, and ad hoc reporting; ODBC/API with authorized analytics role

## Visualization & Reporting
- **Tableau Server / Tableau Cloud** — quality dashboards published by the analytics team; REST API for workbook and data source access with service account credentials
- **Qlik Sense** — interactive analytics for quality metrics; REST API with application credentials
- **Power BI (Microsoft Fabric)** — quality report datasets accessed via REST API or DAX queries with service account

## Quality Measure Specifications
- **NCQA HEDIS Technical Specifications** — measure specifications by domain (effectiveness of care, access, utilization, patient experience); accessed via NCQA API with licensed subscription
- **CMS Quality Payment Program (QPP) / MIPS measures** — measure specifications, benchmarks, performance category weights; public API at qpp.cms.gov
- **CMS Hospital Compare (Care Compare)** — hospital-level quality measure data (mortality, readmissions, HAIs, patient experience, timely care); public data API at data.cms.gov
- **Leapfrog Hospital Survey** — hospital safety grades, Leapfrog-specific measure data; public data files

## Patient Safety Reporting
- **Joint Commission SentinelEvent database** — sentinel event alert summaries, safety goal requirements; public content accessed via Joint Commission website
- **AHRQ Patient Safety Indicators (PSI)** — PSI measure definitions and national benchmark rates; public data at qualityindicators.ahrq.gov

## Data Sources

### HEDIS Measure Performance Data

- **NCQA HEDIS / Health Catalyst** — measure ID (e.g., CDC, BCS, CBP), measure name, measurement year, denominator count, numerator count, rate (%), percentile rank (25th/50th/75th/90th NCQA national), prior year rate, rate change (improvement/decline/stable), care gap patient count, gap closure rate, data completeness flag

### CAHPS Survey Data

- **CMS CAHPS (Hospital, CG, Hospice, etc.)** — survey domain (communication with doctors, communication with nurses, responsiveness, care transitions, overall rating, recommend), mean top-box score, adjusted score, national percentile rank, peer group comparison, response rate, sample size

### CMS Star Ratings & VBP

- **CMS Hospital Compare** — hospital NPI, hospital name, measure domain (mortality, safety, readmissions, patient experience, timely care), measure ID, hospital rate, national rate, state rate, star category (1-5 stars), footnote flags, data period
- **CMS Value-Based Purchasing (VBP)** — domain weights (clinical outcomes, person and community engagement, safety, efficiency), total performance score, payment adjustment percentage, national performance distribution

### Patient Safety Indicators

- **AHRQ PSI** — PSI number and name (e.g., PSI-90 composite, PSI-11 postoperative respiratory failure), observed rate, expected rate, risk-adjusted rate, O/E ratio, national benchmark, flag for outlier status

### Population Health / Care Gaps (aggregated)

- **Innovaccer / Epic Cogito** — care gap measure name, eligible patient count, gap count, gap closure rate, service date of last qualifying event, responsible care team, closure opportunity value (estimated revenue impact), stratification by age, gender, payer, risk tier; minimum cell size enforced (n≥10) before displaying

### Accreditation Readiness

- **Joint Commission / DNV** — standard number (e.g., RC.02.01.01), standard description, compliance status (compliant/partial/non-compliant), evidence of standards compliance (ESC) narrative, last survey date, finding type (requirement for improvement, immediate threat to life), follow-up due date
