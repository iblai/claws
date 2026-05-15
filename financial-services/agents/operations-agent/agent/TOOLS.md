# Tools Reference — Operations Specialist

## Settlement and Post-Trade Platforms

- **DTCC (DTC / NSCC)** — retrieve equity and corporate bond settlement status from DTC; access NSCC Continuous Net Settlement (CNS) queue; pull failed trade reports and buy-in notices; retrieve DK (don't know) alerts and respond via DTC's ID Net matching
- **Fedwire Funds and Securities** — access government securities and agency bond settlement status via Fedwire Securities; retrieve funds transfer confirmations; pull net settlement positions
- **Euroclear / Clearstream** — retrieve cross-border settlement status for international equity and fixed income trades; access custody account balances; pull pending settlement instructions

## Middle/Back Office Systems

- **Advent Geneva** — access book-of-record position data, transaction records, and cost basis; retrieve reconciliation output between Geneva and prime broker/custodian statements; pull P&L summaries and accrual data
- **Broadridge** — access trade processing workflows, settlement instruction status, and exception management queues; retrieve corporate action notifications and election deadlines; pull asset servicing records
- **SS&C AXYS / Eze OMS** — retrieve order management data, trade allocations, and settlement instructions; pull execution reports and broker confirmations for reconciliation matching

## Custodian Interfaces

- **Prime Broker Portal** — retrieve daily prime brokerage statements, stock borrow/loan positions, margin balances, and financing rates; access fails and buy-in notifications; pull stock locate records
- **Custodian Data Feed** — retrieve end-of-day custody account positions, cash balances, pending settlements, and corporate action records for daily reconciliation

## Corporate Actions

- **Broadridge Corporate Actions** — retrieve corporate action notifications (dividends, rights issues, tender offers, mergers, proxy votes); track election deadlines; submit and confirm voluntary election instructions on behalf of the firm's accounts
- **DTCC CA Web** — access DTCC-announced corporate actions; retrieve eligibility and record date information; confirm mandatory and voluntary event processing status

## Data Sources

### Settlement

- **DTCC (DTC/NSCC)** — equity settlement (DTCC participant ID, trade reference, security CUSIP, ISIN, trade date, settlement date, quantity, net amount, settlement status — settled/pending/failed, counterparty, DK flag, buy-in notice date), CNS queue (trade reference, net position, obligation amount, settlement date, failure reason, aged flag)
- **Fedwire Securities** — government securities settlement (trade reference, CUSIP, par value, price, trade date, settlement date, delivering participant, receiving participant, status — settled/pending, Fedwire transfer number)
- **Euroclear / Clearstream** — international settlement (ISIN, trade reference, quantity, trade date, settlement date, depository, settlement status, settlement instruction ID, mismatch flag, penalty flag — CSDR)

### Middle and Back Office

- **Advent Geneva** — book-of-record positions (account ID, security, ISIN/CUSIP, quantity — long/short, cost basis, market value, accrued income, as-of date), transaction log (transaction ID, trade date, settle date, type, security, quantity, price, broker, counterparty, account, allocation, commission, fee), reconciliation breaks (break ID, account, security, break type — price/quantity/accrual/corporate action/timing, book value, custodian value, difference, status, resolution date)
- **Broadridge** — trade processing (trade ID, security, trade date, status, counterparty, fail reason, buy-in exposure, margin call flag), corporate action notifications (event ID, security CUSIP/ISIN, event type, announcement date, record date, ex-date, pay date, election deadline, mandatory/voluntary flag, rate/ratio)
- **SS&C AXYS** — position reconciliation (account, security, system quantity, custodian quantity, break amount, break type, open date, resolved flag), cash reconciliation (account, currency, book cash, custodian cash, difference, break reason)

### Custodian Data

- **Prime Broker Statements** — daily PB statement (account, security, quantity — long/short/pledged, market value, margin balance, financing rate, stock borrow balance, stock loan balance, fails receivable, fails payable)
- **Custodian Data Feed** — end-of-day positions (account, security, ISIN/CUSIP, quantity, market value, accrued interest, currency, as-of date), pending settlements (instruction ID, security, quantity, settlement date, counterparty, status)

### Corporate Actions

- **DTCC CA Web** — corporate action events (event ID, security CUSIP, event type, announcement date, record date, ex-date, pay date, rate, voluntary election deadline, DTC processing status)
- **Broadridge Corporate Actions** — client elections (event ID, account, elected option, election date, election method, confirmation reference, instruction status)

### Audit Trail

- **Operations Audit Log** — (event type — break identified/break resolved/instruction submitted/election made/adjustment booked/escalation raised, trade or account reference, operator ID, timestamp, second reviewer ID if applicable, business justification, counterparty confirmation reference)
