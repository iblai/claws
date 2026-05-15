# Tools Reference — Client Advisor

## Investment Research

- **Morningstar Direct** — access fund and equity research, analyst ratings, ESG scores, sustainability metrics, category performance, and peer comparisons; pull Portfolio X-Ray for holdings overlap analysis
- **FactSet** — retrieve fundamental data, earnings estimates, sector analysis, and custom screening; access FactSet Alpha Testing for strategy backtesting; pull ownership data and institutional flow
- **Bloomberg Intelligence** — access buy-side and sell-side research notes, sector primers, and earnings analysis by ticker or theme

## CRM and Client Data

- **Salesforce Financial Services Cloud** — retrieve client profile, investment objectives, risk tolerance, time horizon, and financial plan data; log advisory interactions and next actions; pull household relationship maps
- **Redtail CRM** — access client contact records, account associations, notes history, and workflow task status; pull upcoming reviews and birthday/anniversary reminders for relationship touchpoints

## Suitability and Proposal Tools

- **Riskalyze / Nitrogen** — run suitability assessment and risk number alignment; compare client's risk tolerance to proposed portfolio; generate Risk Analysis Report for advisor review
- **MoneyGuidePro / eMoney** — access financial plan outputs including goal progress, cash flow projections, and retirement readiness scores; pull scenario comparisons for advisory conversations

## Portfolio Construction

- **Orion Portfolio Solutions** — access model portfolios, rebalancing proposals, and tax-loss harvesting opportunities; retrieve account-level drift reports against target allocation
- **iRebal** — pull rebalancing trade recommendations; retrieve tax overlay instructions and sleeve-level targets for review by the advisor

## Data Sources

### Client Profile and CRM

- **Salesforce Financial Services Cloud** — client profile (client ID, name, household, relationship manager, segment, AUM, date of birth, contact), investment objectives (goal type, target amount, time horizon, priority), risk profile (risk tolerance score, risk category, last assessment date, suitability review date), account relationships (account number, account type, custodian, status, opened date, linked household)
- **Redtail CRM** — contact records (client ID, name, contact info, birthday, advisor, office), notes history (note ID, date, author, subject, content, linked account), workflow tasks (task ID, due date, assigned to, status, action type)

### Investment Research

- **Morningstar Direct** — fund data (ticker, name, category, star rating, analyst rating, Morningstar Sustainability Rating, expense ratio, inception date, AUM, benchmark), performance data (fund ID, period, total return, category rank, benchmark return, alpha, beta, Sharpe ratio), holdings data (fund ID, holding name, weight, sector, country, market cap, asset class)
- **FactSet** — equity fundamentals (ticker, revenue, EPS, P/E, P/B, EV/EBITDA, debt/equity, dividend yield, consensus estimates), sell-side research (report ID, analyst, firm, ticker, rating, price target, summary), earnings calendar (ticker, fiscal period, report date, estimated EPS, actual EPS, surprise)

### Suitability

- **Riskalyze / Nitrogen** — suitability data (client ID, Risk Number, assessment date, portfolio risk number, alignment gap, proposed allocation risk number, suitability assessment outcome, advisor notes)
- **MoneyGuidePro** — financial plan data (plan ID, client ID, goals, assets, liabilities, income, expenses, savings rate, retirement date, retirement readiness score, Monte Carlo probability)

### Model Portfolios

- **Orion Portfolio Solutions** — model portfolio data (model ID, name, benchmark, target allocations by asset class, rebalancing bands, last rebalanced, YTD return, risk metrics)
- **Morningstar Managed Portfolios** — managed account data (sleeve ID, strategy, benchmark, holdings, performance, expense ratio, minimum investment, eligible account types)
