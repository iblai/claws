# Tools

## Federal Aid Systems

- **StudentAid.gov API** — retrieve FAFSA status (submitted, processed, selected for verification), Student Aid Index (SAI), dependency status determination, Pell Grant eligibility estimate
- **COD (Common Origination and Disbursement)** — Direct Loan origination and disbursement records, award year data, aggregate loan totals

## SIS Financial Aid Module

- **Banner Financial Aid (Ellucian)** — student aid package (grants, loans, work-study by award year), satisfactory academic progress (SAP) status, verification requirements, disbursement schedule, R2T4 calculation inputs
- **PeopleSoft Campus Solutions** — award summary, budget (cost of attendance components), need analysis data, packaging history
- **Workday Student** — financial aid awards, payment plan enrollment, account balance, pending disbursements

## Scholarship Matching

- **Institutonal Scholarship Database** — query scholarship criteria (GPA minimum, major, demographic, essay requirement, deadline), match student profile to eligible awards, track application status
- **Fastweb / Scholarships.com** — external scholarship search by eligibility profile; returns scholarship name, award amount, deadline, eligibility criteria, application URL

## Document Management

- **Verification document portal** — request and track submission of verification documents (tax transcripts, W-2s, identity documents), update verification status in Banner/PeopleSoft

## Data Sources

### Federal Aid Data

- **FAFSA (StudentAid.gov)** — student and contributor financial data (AGI, tax filing status, assets, household size, number in college), dependency status, SAI, Pell Grant eligibility, verification selection flag, ISIR transaction history
- **NSLDS (National Student Loan Data System)** — aggregate loan totals (subsidized, unsubsidized, PLUS), loan servicer information, default status, enrollment deferment history, overpayment flags

### Institutional Financial Aid Records

- **Banner Financial Aid / PeopleSoft** — cost of attendance (tuition, fees, room, board, books, personal, transportation by student type), aid package by award year (grants, scholarships, loans, work-study — amount awarded, accepted, cancelled, disbursed), satisfactory academic progress history (GPA, completion rate, max timeframe), verification tracking (selected, document requirements, cleared date), R2T4 data (withdrawal date, last date of attendance, earned vs. unearned aid calculation)

### Scholarship Data

- **Institutional scholarship database** — scholarship name, fund source, award amount (fixed or variable), eligibility criteria, application requirements, deadline, renewable conditions, prior recipients
- **State grant programs** — state-specific grant eligibility rules (residency, enrollment status, GPA), award amounts, renewal conditions (varies by state)
- **External scholarship feeds (Fastweb, Scholarships.com)** — award name, sponsoring organization, amount, deadline, eligibility tags (major, GPA, demographic, essay, community)

### Student Financial Records

- **SIS student account** — current balance due, payment plan enrollment, holds affecting registration, payment history, refund status
- **1098-T data** — tuition payments and scholarships reported for tax purposes (reference only; direct to tax professional for interpretation)
