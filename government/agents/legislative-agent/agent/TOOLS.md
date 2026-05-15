Available integrations for legislative and regulatory analysis:

- **Congress.gov API** — search and retrieve bill details, status, sponsors, co-sponsors, committee referrals, hearing schedules, floor actions, votes, and full bill text by Congress session and bill number
- **GovInfo API** — retrieve enrolled bill text, conference reports, Congressional Record excerpts, and committee hearing transcripts
- **Federal Register API** — track rulemaking actions (proposed rules, final rules, interim final rules, NOPRs) by agency and program area; retrieve comment periods and regulatory agenda items
- **Regulations.gov** — access public comments on proposed rules, docket documents, and agency response summaries
- **CRS Reports (crsreports.congress.gov)** — retrieve Congressional Research Service nonpartisan analysis on legislation and policy areas
- **Agency legislative tracking system** — internal watch list of bills and rulemakings affecting agency programs; annotation with agency impact assessments and official positions (internal use)
- **State legislature API (LegiScan / OpenStates)** — track state-level bills and status across all 50 states + DC for programs with state counterpart requirements

## Data Sources

Systems and platforms for legislative tracking and regulatory analysis.

### Federal Legislation

- **Congress.gov API** — bills (bill ID, number, type: HR/S/HJRES/SJRES, title, summary, sponsor, co-sponsors, committees referred, latest action, latest action date, status stage, related bills, subjects, policy area), actions (action date, action description, action type, committee, vote result), amendments (amendment number, sponsor, purpose, status), text versions (version type, date, format, URL)
- **GovInfo** — enrolled acts (public law number, enacted date, full text, CFR amendments directed), Congressional Record (date, chamber, speaker, text, pages), committee prints (committee, title, date, full text), hearing transcripts (hearing title, committee, date, witnesses, testimony text)

### Regulatory Tracking

- **Federal Register API** — documents (document number, type: rule/proposed rule/notice, agency, title, publication date, effective date, CFR parts affected, RIN, docket ID, significant rule flag per EO 12866, summary, full text, comment period open/close dates), unified regulatory agenda (RIN, agency, title, stage: pre-rule/proposed rule/final rule/long-term, abstract, planned action date)
- **Regulations.gov** — dockets (docket ID, agency, title, type, last modified), documents (document ID, title, type, comment count, posted date), public comments (comment ID, commenter type, text, attachments, posted date), comment period analytics (total comments, comment rate, commenter categories)

### State Legislation

- **LegiScan / OpenStates** — state bills (bill ID, state, session, number, title, status, last action date, sponsors, subjects, text versions, votes, committee assignments), state sessions (session name, start date, end date, sine die flag)

### Agency Legislative Affairs

- **Internal watch list** — tracked items (bill/rule ID, relevance category, assigned analyst, impact assessment summary, agency position: support/oppose/neutral/monitoring, last updated, Congressional contact log)
