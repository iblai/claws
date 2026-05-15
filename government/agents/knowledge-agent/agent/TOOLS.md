Available integrations for policy and knowledge retrieval:

- **Sharepoint / Confluence / M-Files** — full-text semantic search across the agency document library; retrieve document metadata (title, version, effective date, owner), download document content, and list related documents
- **Federal Register API (federalregister.gov)** — search and retrieve federal rules, proposed rules, notices, and executive orders by agency, date range, or CFR citation
- **eCFR API (ecfr.gov)** — retrieve current Code of Federal Regulations text by title, chapter, part, and section; check amendment history
- **GovInfo API (govinfo.gov)** — retrieve public laws, congressional bills, GAO reports, and other federal publications by package ID or full-text search
- **Agency SOP / directive repository** — versioned internal SOPs, memos, and directives stored in the agency document management system; supports filtering by category, issuing office, and effective date range
- **Records retention schedule lookup** — query the agency records retention schedules to determine retention periods, disposition instructions, and applicable legal holds

## Data Sources

Systems and platforms for policy, SOP, and procedure retrieval.

### Internal Document Management

- **SharePoint (Government)** — document library (document ID, title, content type, site collection, library, folder path, version number, version history, author, last modified by, last modified date, approval status, sensitivity label, retention label, document content as text), search index (keyword relevance score, semantic similarity score, suggested related documents)
- **M-Files** — document vault (object ID, class, title, metadata properties: effective date, issuing office, document type, classification level, review cycle, superseded-by pointer, status: draft/approved/superseded/archived), workflow state (current workflow state, approver, approval date, comments), version history (version number, changed by, change date, change description)

### Federal & Regulatory Sources

- **Federal Register API** — notices/rules (document number, type: rule/proposed rule/notice/presidential document, agency, title, publication date, effective date, RIN, CFR references, full text, comment deadline, docket ID)
- **eCFR API** — CFR sections (title, chapter, part, section, subpart, section text, amendment date, source authority, cross-references), amendment history (amendment action, Federal Register citation, effective date)
- **GovInfo** — packages (package ID, document type, congress, date, granule count), statutes (public law number, enacted date, full text, amendments), GAO reports (report number, title, subject, recommendations, agency responses)

### Internal Policy Catalog

- **Agency directive registry** — directives (directive number, title, type: policy/procedure/guidance/form, issuing office, effective date, expiration date, review date, supersedes list, summary, full text, classification: public/internal-use/law-enforcement-sensitive/exempt-from-FOIA)
- **Records retention schedules** — schedule items (schedule number, series title, disposition authority, retention period: trigger event + years, final disposition: destroy/transfer-to-archives, legal hold flag, applicable CFR/USC citations)
