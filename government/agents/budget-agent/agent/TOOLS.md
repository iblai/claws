Available integrations for government budget and financial management:

- **Oracle Federal Financials / SAP Concur Government Edition / CGI Momentum** — query fund balances, obligations, expenditures, and available authority by appropriation, fund account, cost center, and object class; retrieve purchase order and obligation details; generate standard financial reports
- **Travel management system (E2 Solutions / Concur Travel)** — check travel authorization status, per diem rates, and travel voucher processing status; retrieve travel spending by employee or cost center
- **Purchase card (GPC) management (Access Online / Citibank Government)** — view GPC transaction detail, monthly statement status, accountholder credit limits, and policy compliance flags
- **USASpending.gov API** — retrieve public spending data for budget transparency reporting; cross-check agency obligation data against public disclosure
- **OMB MAX / GTAS** — access Governmentwide Treasury Account Symbol (GTAS) reporting submissions, SF-133 data, and budget execution reports
- **Sam.gov** — verify vendor registrations, DUNS/UEI numbers, and active exclusions before obligating funds
- **Agency approvals workflow** — route and track purchase approval requests through the required certification and approval chain

## Data Sources

Systems and platforms for government budget execution and financial management.

### Core Financial System

- **Oracle Federal Financials / CGI Momentum** — fund accounts (Treasury Account Symbol, appropriation year, appropriation title, total budget authority, obligated amount, expended amount, unobligated balance, reimbursable vs. direct), obligations (obligation document number, type: contract/grant/IAA/purchase order, vendor/recipient, obligated amount, liquidated amount, unliquidated obligation, fund, object class, program activity, project), expenditures (payment date, amount, vendor, invoice number, fund, object class), budget object class (OMB 3-digit object class, title, amounts by object class for reports)
- **GTAS / SF-133** — budget execution data (TAFS, prior year, current year, budget authority, obligations, outlays by period), SF-133 line items (line number, description, amount, fund source)

### Travel & Purchase Card

- **E2 Solutions / Concur Travel** — travel authorizations (authorization number, traveler, trip purpose, destination, travel dates, estimated cost, approval status, fund citation), travel vouchers (voucher number, authorization number, expense items, amounts claimed, per diem amounts, receipt attachments, payment status), per diem rates (location, lodging rate, meals and incidentals rate, effective date)
- **GPC Management (Access Online)** — transactions (transaction date, merchant, amount, MCC, account holder, billing address, purchase description, receipt attached, approver, reviewed status), statements (billing cycle, total charges, credit limit, available credit, limit exception requests)

### Transparency & Vendor

- **USASpending.gov API** — awards (award ID, type: contract/grant/loan, recipient, awarding agency, funding agency, amount, start/end date, NAICS, PSC, location), sub-awards, agency financial assistance data
- **SAM.gov** — entity registrations (UEI, legal business name, CAGE code, physical address, registration status, expiration date, active exclusion flag, SAM purpose of registration, NAICS codes)
