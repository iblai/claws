# Tools

## Admissions Platform — Slate (Technolutions)

Read application materials, scores, and reviewer notes.

- Retrieve complete application records: bio data, academic history, test scores, essays, recommendations, activities list
- Read school profile data (Naviance/Scoir) for context on GPA scale and course availability
- Write reader scores and notes back to the application record
- Pull cohort statistics for percentile benchmarking

## Document Processing

- Parse PDF and image transcripts using OCR; extract course names, grades, credit hours, and GPA
- Identify grade trends across semesters (upward, downward, plateau)
- Detect Advanced Placement, IB, dual-enrollment, and honors course designations
- Calculate recalculated GPA on institutional scale

## Common App / Coalition API

- Retrieve submitted application data in structured JSON format
- Access self-reported academic record and honors/awards sections
- Pull recommender letters and counselor school report

## Scoring Engine

- Apply institutional rubric weights to academic, extracurricular, essay, and recommendation scores
- Generate composite application score with component breakdown
- Flag applications outside scoring confidence bounds for human escalation

## Data Sources

### Application Platforms

- **Common App** — applicant bio data (name, address, DOB, citizenship, first-gen indicator), academic history (school name, GPA, class rank, graduation date), test scores (SAT/ACT, AP/IB scores), activities list (category, role, hours/week, description), personal statement, additional information essay, recommender letters, counselor school report
- **Slate (Technolutions)** — application checklist status (required materials received/missing), reader assignments, prior review notes, cohort percentile ranks, decision history
- **Coalition App** — same core fields as Common App; locker portfolio (uploaded writing samples, projects, media)

### Academic Record Data

- **Naviance (Hobsons) / Scoir** — school profile (mean GPA, class rank policy, grading scale), historical send data (prior applicants' stats and decisions), teacher/counselor recommendation tracking
- **College Board** — AP exam scores (subject, score 1-5, year taken), SAT score reports (EBRW, Math, total, section scores, subscores, cross-test scores), Student Search data
- **ACT** — composite and section scores (English, Math, Reading, Science), writing score, superscored composite

### Institutional Rubrics

- **Internal scoring rubric** — criteria weights for: academic achievement, course rigor, grade trend, test scores, extracurricular depth, essay quality, recommendation strength, institutional fit indicators; stored in institutional knowledge base
- **Cohort benchmarks** — prior-year admitted, denied, and waitlisted applicant distributions by program; used for percentile scoring and comparative analysis
