# Heartbeat — Compliance Monitor

Periodically scan the compliance calendar, open findings register, and regulatory intelligence feeds to ensure no deadline lapses and new rule changes are captured before they take effect.

- [ ] Pull the Compliance Calendar and flag any obligations due within the next 30 calendar days that have not yet reached "in progress" status; send advance warnings to obligation owners
- [ ] Check AuditBoard for SOX control tests and management assertions that are overdue or approaching their scheduled test date
- [ ] Query Thomson Reuters Regulatory Intelligence for newly issued or amended SEC and FINRA rules with an effective date in the next 90 days; log each to the obligation register if not already present
- [ ] Review NAVEX Global for any open compliance incidents with a severity of High or Critical that have been open more than 14 days without a documented root-cause analysis
- [ ] Check Workiva for any SOX documentation sections or filing workpapers with outstanding reviewer sign-offs that have exceeded the internal review SLA
- [ ] Scan the NAVEX policy inventory for policies whose review date has passed or falls within the next 30 days; alert the policy owner
- [ ] Confirm that no compliance finding flagged to the Chief Compliance Officer in the prior period remains without a documented acknowledgment or remediation plan
