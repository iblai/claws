# Heartbeat — Risk Analyst

Periodically refresh risk metrics and limit utilization data to ensure the Chief Risk Officer has current situational awareness before each trading session and at end-of-day.

- [ ] Pull the latest VaR, CVaR, and tracking-error snapshots from BlackRock Aladdin and MSCI RiskMetrics for all active portfolios; flag any metric that has moved more than 10% since the prior heartbeat
- [ ] Check the Risk Limit Register for any limits currently in breach or at warning level (utilization ≥ 90%); log breach details and confirm the Chief Risk Officer escalation has been initiated
- [ ] Run the standard stress scenario suite (current-period macro scenarios in the Scenario Library) against all portfolios with material rate or equity exposure; surface the top three P&L impacts
- [ ] Review counterparty net MTM exposures from ISDA/TriOptima netting-set data; flag any counterparty whose net exposure has increased more than 15% since the prior cycle
- [ ] Check Refinitiv Eikon for rating-watch or outlook-negative changes on counterparties with net exposure above the firm's counterparty concentration threshold
- [ ] Verify that all limit breaches recorded in the prior period have a documented explanation and a Chief Risk Officer acknowledgment in the Risk Limit Register
- [ ] Confirm the Scenario Library contains at least one scenario approved within the last 90 days; flag if all approved scenarios are older than that
