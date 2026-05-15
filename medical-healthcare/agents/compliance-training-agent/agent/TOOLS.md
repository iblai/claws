# Tools Reference — Compliance Training Agent

## Learning Management Systems (LMS)
- **HealthStream** — healthcare-specific LMS with HIPAA, OIG, CMS Conditions of Participation, and Joint Commission training libraries; completion tracking, competency assessments, credential expiration alerts; REST API with facility admin credentials
- **Relias** — compliance and clinical training courses; transcript management, group assignment, automated renewal reminders; REST API
- **Cornerstone OnDemand / SAP SuccessFactors Learning** — enterprise LMS for broader compliance curriculum delivery and reporting; REST API

## HR & Identity Systems
- **Workday HCM** — employee job title, department, hire date, employment status; used to determine required training tracks by role; read-only REST API
- **Azure Active Directory** — role group membership to assign compliance training curricula by department and function

## Regulatory Reference Sources
- **HHS Office for Civil Rights (OCR) HIPAA guidance** — public REST endpoint (hhs.gov); fetches current Privacy Rule, Security Rule, and Breach Notification Rule summaries
- **CMS Conditions of Participation** — public endpoint (cms.gov); regulation text, interpretive guidelines
- **OIG Compliance Program Guidance** — public endpoint (oig.hhs.gov); industry-specific guidance documents

## Policy Repository
- **SharePoint / Confluence (on-premises)** — organizational policies and procedures; searched by keyword or regulation cross-reference; read-only API with service account credentials

## Certification Tracking
- **HealthStream Transcript API** — per-user completion records (course name, completion date, score, certificate expiration, required vs. elected, assigned vs. self-enrolled)

## Data Sources

### LMS Completion & Transcript Data

- **HealthStream** — employee ID (hashed), course ID, course title, course category (HIPAA/privacy, infection control, patient safety, CMS CoP, OIG, fire safety, etc.), assigned date, due date, completion date, pass/fail, score (%), certificate number, expiration date, assignment source (required/role-based/self-enrolled), completion method (online/classroom/competency check)
- **Relias** — same fields as HealthStream plus curriculum groupings and group completion rate aggregates (no individual PHI in aggregate reports)

### HR / Workforce Data (read-only, minimum necessary)

- **Workday HCM** — employee ID, department, job family, job profile, hire date, employment status (active/leave/terminated); used only to determine applicable training track; no salary or personal health data
- **Azure AD groups** — group name, group type, member count; used for bulk training assignment routing

### Regulatory Reference Content

- **HHS OCR HIPAA Rules** — rule name (Privacy/Security/Breach Notification/Enforcement), CFR citation (45 CFR Part 160/164), section title, summary text, effective date, last updated date, applicable entity type (covered entity, business associate)
- **CMS Conditions of Participation** — regulation number, condition title, interpretive guideline text, surveyor guidance, effective date, applicable provider type
- **OIG Compliance Guidance** — document title, target industry, publication date, key risk areas, recommended program elements, safe harbor references

### Policy Repository

- **SharePoint / Confluence** — document title, document ID, version, effective date, review date, owning department, regulation cross-references (CFR citations), policy category, approval status
