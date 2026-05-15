# Tools Reference — Regulatory Reporter

## Regulatory Filing Platforms

- **Workiva (Wdesk)** — draft, review, and version-control SEC filings (Form ADV, 13F, 13D/G, 8-K, annual reports); manage XBRL tagging and inline XBRL; track reviewer sign-offs and certification chain before submission
- **Wolters Kluwer OneSumX** — prepare and validate regulatory capital and liquidity reports (CCAR, FR Y-9C, Call Report, BCBS 239); access regulatory calculation engines; submit to regulators via OneSumX workflow
- **EDGAR Filing System** — access SEC EDGAR API for filing status queries, prior submission retrieval, and filing acknowledgment confirmation

## Internal Data Sources

- **Order Management System (OMS)** — pull executed trade data, position snapshots, and transaction history for 13F and large trader reporting
- **General Ledger / ERP** — retrieve balance sheet, P&L, and capital data for call report and CCAR submissions
- **Custodian Data Feed** — pull end-of-day holdings, cash balances, and corporate action records for regulatory position reporting

## AML/BSA Filing

- **FinCEN BSA E-Filing System** — prepare and validate Suspicious Activity Reports (SAR) and Currency Transaction Reports (CTR) for BSA Officer review and submission; retrieve prior filing status and acknowledgment
- **Case Management System** — retrieve investigation summaries, supporting documentation, and narrative inputs for SAR preparation

## Deadline and Audit Management

- **Compliance Calendar** — track all regulatory filing deadlines with advance warning logic (30/14/3 business days); log filing milestones, submitter, reviewer, and submission timestamp in the master audit trail

## Data Sources

### Regulatory Filing Platforms

- **Workiva (Wdesk)** — filing inventory (filing ID, type, regulation, reporting period, preparer, reviewer, status, due date, submission date, EDGAR confirmation number), workpaper linkage (data point, source system, last refreshed, linked cell reference, reviewer sign-off), XBRL tagging (element, tag, value, period, context, calculation linkbase validation status)
- **Wolters Kluwer OneSumX** — regulatory calculation outputs (report type, regulation, reporting period, calculated value, validation rule, error/warning count, submission status, regulatory acknowledgment), capital and liquidity data (capital ratio type, tier, RWA, capital amount, requirement, buffer, excess/shortfall)

### Transaction and Position Data

- **Order Management System (OMS)** — trade data (trade ID, security, ISIN/CUSIP/FIGI, trade date, settlement date, direction, quantity, price, counterparty, broker, account, allocation), large trader data (trader ID, account, security, aggregate long/short position, report threshold, report date)
- **General Ledger / ERP** — balance sheet (account, entity, period, debit, credit, balance, currency), P&L (revenue, expense, net income by line item and entity, period), capital accounts (equity, retained earnings, regulatory capital components)

### AML/BSA Filing

- **FinCEN BSA E-Filing** — SAR records (SAR ID, filing date, BSA Officer signatory, suspicious activity type, amount, subject details, account involved, narrative summary, filing status, confirmation number), CTR records (CTR ID, filing date, transaction date, amount, cash-in/cash-out, conductor, beneficiary, filing status)
- **Case Management System** — investigation records (case ID, subject, account, investigation type, findings summary, SAR referral recommendation, analyst, supervisor review, closure date)

### Audit Trail

- **Filing Audit Log** — (filing ID, version, action type — created/revised/approved/submitted, actor ID, timestamp, change summary, data sources snapshot, regulatory acknowledgment reference)
- **Compliance Calendar** — (filing type, regulation, reporting period, due date, advance warning dates, preparer assigned, reviewer assigned, current status)
