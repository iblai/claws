# Tools Reference — Risk Analyst

## Risk Analytics Platforms

- **BlackRock Aladdin** — query portfolio-level risk metrics (VaR, CVaR, tracking error, factor exposures, stress scenarios); retrieve risk decomposition reports; run custom scenario analyses using Aladdin's stress testing engine
- **MSCI RiskMetrics** — access parametric and historical VaR models; retrieve factor risk reports; pull liquidity-adjusted risk metrics; run Basel capital charge estimates
- **Axioma Portfolio Analytics** — run factor-based risk decomposition; compare portfolio risk against benchmark; access multi-asset class risk models; generate systematic vs. idiosyncratic breakdown

## Market Data

- **Bloomberg Terminal API** — retrieve real-time and historical price data, volatility surfaces, credit spreads, rates curves, and commodity prices for scenario parameterization
- **Refinitiv Eikon** — pull fundamental data, credit ratings, and counterparty financial metrics; retrieve cross-asset market data for stress scenario construction

## Portfolio Management Systems

- **Charles River IMS** — access live portfolio positions, exposures, and benchmark weights; retrieve order management data for pre-trade risk analytics
- **StatPro Revolution** — pull return and risk time series; retrieve factor attribution results; access compliance monitoring output

## Counterparty Risk

- **ISDA Amend / TriOptima** — retrieve ISDA master agreement data and netting set exposures; access initial margin calculations for uncleared derivatives
- **IHS Markit Credit Risk** — pull CDS spreads, credit rating changes, and counterparty PD estimates for exposure management

## Data Sources

### Portfolio Risk Platforms

- **BlackRock Aladdin** — risk decomposition (portfolio ID, date, factor model, VaR, CVaR, tracking error, beta, duration, DV01, factor contributions, residual risk), stress test results (scenario name, shock parameters, portfolio P&L impact, sector impact, top contributors/detractors), limit monitoring (limit ID, metric, limit value, current value, utilization percentage, breach flag, breach date)
- **MSCI RiskMetrics** — parametric VaR (confidence level, holding period, methodology, portfolio value, VaR amount, CVaR), historical simulation (window, number of scenarios, portfolio P&L distribution, tail loss estimate), incremental VaR (security ID, IVAR contribution, marginal contribution to risk, diversification benefit)
- **Axioma** — factor model output (factor name, factor return, factor exposure, factor risk contribution, specific risk, total risk), active risk decomposition (systematic active risk, specific active risk, total active risk, information ratio, active share)

### Market Data

- **Bloomberg** — price data (security ID, FIGI, close price, bid/ask, currency, source), volatility surfaces (underlying, expiry, strike, implied vol, delta, vega), rates curves (curve ID, tenor, rate type, date, value), credit spreads (issuer, seniority, currency, tenor, OAS, Z-spread)
- **Refinitiv Eikon** — counterparty financials (entity ID, LEI, revenue, assets, debt, EBITDA, rating, outlook, CDS spread), sector data (sector, index, price, P/E, EV/EBITDA, debt/equity, dividend yield)

### Counterparty and Credit Risk

- **ISDA/TriOptima** — netting set data (counterparty LEI, master agreement type, netting qualifier, gross MTM, net MTM, initial margin, variation margin, regulatory capital charge)
- **IHS Markit** — CDS curves (reference entity, seniority, currency, tenor, mid spread, upfront, recovery rate), ratings data (entity, current rating, outlook, watch status, last change date, agency)

### Internal Risk Limits

- **Risk Limit Register** — (limit ID, portfolio, metric, strategy, limit value, warning level, breach escalation, owner, approval date, policy reference)
- **Scenario Library** — (scenario ID, name, type — historical/hypothetical, shock definitions, approval date, intended use, last run date)
