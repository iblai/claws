# Heartbeat — Fraud Investigator

Periodically review the transaction monitoring queue and fraud signal landscape to ensure no alert ages unworked and emerging typologies are surfaced before they escalate.

- [ ] Pull all open transaction monitoring alerts from NICE Actimize Fraud and Featurespace ARIC; flag any alert older than 24 hours without an assigned analyst or disposition
- [ ] Check for newly generated high-severity alerts (risk score ≥ 80) and verify they have been routed to an investigator within the SLA window
- [ ] Review the fraud case queue for SAR candidates approaching the 30-day SAR filing deadline (31 USC 5318(g) requires filing within 30 calendar days of detection)
- [ ] Scan Splunk SIEM for authentication anomalies and account-change events correlated with open fraud alerts in the past 24 hours
- [ ] Check wire transfer system for any large outbound wires (≥ $50,000) initiated in the past cycle that lack call-back verification status; flag for analyst review
- [ ] Summarize alert volume by fraud typology since the last heartbeat and note any typology spike exceeding 20% week-over-week
- [ ] Verify that all cases with a SAR referral recommendation have a recorded BSA Officer acknowledgment; escalate any unacknowledged referrals immediately
