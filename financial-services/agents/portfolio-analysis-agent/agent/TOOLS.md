# Tools Reference — Portfolio Analyst

## Performance Analytics Platforms

- **StatPro Revolution** — run time-weighted and money-weighted return calculations; execute Brinson-Hood-Beebower attribution; retrieve sector, country, and security selection/allocation effects; generate GIPS-compliant composite reports
- **BlackRock Aladdin Performance** — access factor-based return decomposition; retrieve systematic vs. idiosyncratic alpha; run attribution across equities, fixed income, and multi-asset portfolios
- **Advent Axys / Geneva** — pull portfolio accounting data, cost basis records, and transaction history; retrieve composite performance data; access reconciled NAV time series

## Market Data and Benchmarks

- **MSCI Benchmark Indices** — access index constituents, weights, and returns for MSCI World, EM, and factor indices; retrieve benchmark characteristics for active share and tracking error analysis
- **Bloomberg Barclays Index Services** — pull fixed income benchmark data (Agg, Credit, High Yield, Duration-Matched); retrieve spread and duration attribution inputs
- **FactSet** — access total return data, dividend data, and fundamental metrics for attribution model inputs; retrieve sector classification and benchmark mapping

## Portfolio Management Systems

- **Orion** — access account-level returns, holdings, and benchmark assignments; retrieve client-level composite groupings; pull fee calculations and net-of-fee return series
- **Morningstar Direct** — run manager due diligence comparisons; access peer universe rankings; retrieve Morningstar style box and factor exposure for external manager analysis

## Reporting

- **GIPS Verification Data Store** — retrieve composite definitions, inclusion/exclusion logs, and firm-wide asset records needed for annual GIPS compliance verification

## Data Sources

### Portfolio Accounting and Returns

- **Advent Geneva** — account positions (account ID, security, ISIN, quantity, cost basis, market value, accrued income, currency, as-of date), transaction history (transaction ID, trade date, settle date, type, security, quantity, price, realized gain/loss), NAV data (fund ID, NAV date, NAV per share, total assets, expense accrual, distribution)
- **Orion** — account returns (account ID, period, beginning value, net contributions, ending value, time-weighted return, money-weighted return, benchmark return, net-of-fee return), composite data (composite ID, member accounts, composite return, composite assets, dispersion, number of accounts)
- **StatPro Revolution** — attribution output (portfolio, benchmark, period, allocation effect, selection effect, interaction effect, total active return, cumulative attribution), risk metrics (tracking error, information ratio, beta, alpha, Sharpe ratio, Sortino ratio, maximum drawdown)

### Benchmark Data

- **MSCI** — index constituents (index ID, date, security name, ISIN, weight, sector, country, market cap, style scores, factor exposures), index returns (index ID, period, total return, price return, dividend return, currency)
- **Bloomberg Barclays Index Services** — fixed income index data (index ID, maturity bucket, credit quality, duration, yield, spread, OAS, total return by period), constituent data (ISIN, weight, duration contribution, sector, rating, coupon, maturity date)
- **FactSet** — sector and industry classification (security, GICS sector, GICS industry, sub-industry), consensus data (security, EPS estimate, revenue estimate, next earnings date, analyst count)

### Factor and Attribution Models

- **BlackRock Aladdin Performance** — factor returns (factor name, period, return, t-stat, model version), security factor loadings (security, factor, loading, contribution to systematic return), active factor exposures (portfolio vs. benchmark factor exposure differences)
- **MSCI Barra** — factor model data (model name, factor, monthly factor return, standard deviation, factor covariance matrix date, model update date)

### GIPS Compliance

- **GIPS Composite Records** — (composite ID, composite definition, inclusion criteria, member accounts, composite return, composite assets, firm assets, three-year annualized ex-post standard deviation, number of accounts, percentage of non-fee-paying accounts, significant cash flow policy)
