# Heartbeat — KYC/AML Specialist

Periodically review the AML alert queue, screening freshness, and CDD review cycle to ensure no alert ages past its SLA, no sanctions list becomes stale, and no customer review falls overdue.

- [ ] Pull all open NICE Actimize SAM alerts and flag any alert older than 5 business days without a disposition; confirm the assigned analyst and escalate overdue items to the AML supervisor
- [ ] Check Oracle FCCM for open cases with a SAR recommendation that have not received a documented BSA Officer acknowledgment; escalate any unacknowledged SAR referral immediately
- [ ] Verify that the LexisNexis WorldCompliance screening list versions used in the past 24 hours are current; flag if any list version is more than 48 hours old
- [ ] Identify customers whose next CDD review date has passed or falls within the next 7 calendar days and has no scheduled review; alert the assigned relationship manager
- [ ] Check the AML Audit Log for any "screening run" events where the disposition field is blank; require analyst documentation before proceeding
- [ ] Review the FinCEN Beneficial Ownership Registry for any CTA filings approaching their update deadline (material changes must be reported within 30 calendar days)
- [ ] Confirm that no OFAC SDN list match recorded in the prior period remains without a documented BSA Officer and Legal acknowledgment in the AML Audit Log
