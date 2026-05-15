# Tools Reference — Knowledge Librarian

## Internal Knowledge Bases

- **Confluence** — search and retrieve internal policy documents, procedure manuals, compliance handbooks, team wikis, and project documentation; access version history and page authorship metadata; retrieve space-level access permissions
- **SharePoint** — search the firm's document management library; retrieve policy documents, forms, templates, and procedure guides by title, keyword, or document ID; access version history and approval workflow status
- **Guru** — retrieve verified knowledge cards from the firm's real-time knowledge base; access card verification status, expert owner, and last-verified date; search by topic, team, or regulation tag

## Policy Management Systems

- **NAVEX PolicyTech** — retrieve policy records including title, version, effective date, owner, review date, and acknowledgment rate; check policy lifecycle status (draft, under review, active, retired); access policy distribution and attestation records
- **PowerDMS** — retrieve accreditation-mapped policy documents; access control-to-policy mapping for compliance evidence; pull version history and approval chain documentation

## Regulatory Reference Libraries

- **Thomson Reuters Practical Law** — retrieve regulatory plain-language summaries, practice notes, and compliance checklists for SEC, FINRA, FinCEN, CFTC, and FDIC regulations; access jurisdiction-specific requirement guides
- **Wolters Kluwer Banking Compliance Library** — retrieve compliance management guidance, regulatory update summaries, and model policies for financial institutions

## Search and Retrieval

- **Semantic Search Engine** — run natural language queries across the full policy and procedure corpus; retrieve ranked results with source document, section, and page reference; flag superseded documents in results
- **Document Expiry Monitor** — retrieve all policies and procedures approaching their scheduled review date within a configurable window; alert the policy owner and Compliance team

## Data Sources

### Policy and Procedure Library

- **NAVEX PolicyTech** — policy records (policy ID, title, category, version number, effective date, review date, owner department, owner name, audience, linked regulations, acknowledgment rate, status — active/under review/retired, distribution list, approval chain)
- **PowerDMS** — procedure documents (document ID, title, type — policy/procedure/form/job aid, owner, status, effective date, review cycle, linked accreditation standards, approval workflow history, current approver)
- **SharePoint Document Library** — internal documents (document ID, title, content type, site, library, folder path, version, modified by, modified date, access level, metadata tags, retention label)

### Knowledge Base

- **Confluence** — wiki pages (page ID, title, space, author, created date, last modified, labels, parent page, child pages, version history, access permissions, linked Jira issues)
- **Guru** — knowledge cards (card ID, title, content, owner, team, verification status, last verified date, verifier, tags, collection, view count, last accessed)

### Regulatory Reference

- **Thomson Reuters Practical Law** — guidance documents (document ID, title, regulation, jurisdiction, topic, document type — practice note/checklist/standard clause, last reviewed date, expert author, related regulations)
- **Wolters Kluwer Banking Compliance Library** — compliance guidance (topic, regulation, jurisdiction, plain-language summary, checklist items, model policy language, penalty overview, enforcement trends, last updated)

### Document Metadata

- **Document Expiry Monitor** — review-due records (document ID, title, owner, scheduled review date, days until review, last reviewer, escalation status, notification sent flag)
- **Supersession Registry** — (document ID, superseded by document ID, effective date of supersession, reason for supersession, owner who approved, archived location)

### Search Index

- **Semantic Search Corpus** — indexed documents (document ID, source system, title, section, page, text excerpt, embedding vector, access level, last indexed date) — used for natural language queries across the full policy and procedure corpus
