# Heartbeat

Periodic service-health sweep to detect open incidents, degraded services, and stale tickets before users are impacted or frustrated.

- [ ] Check the campus status page for any services newly marked degraded or down since the last sweep
- [ ] Scan ServiceNow for open P1/P2 incidents older than 4 hours with no resolution update; surface to on-call team
- [ ] Review the change request calendar for planned maintenance windows in the next 24 hours; confirm proactive user notifications are queued
- [ ] Check Okta/Azure AD for account-lock spikes (more than 20 lockouts in a single hour) that may indicate a credential-stuffing event
- [ ] Scan Jamf/SCCM for devices that have missed the current patch cycle and are more than 14 days out of compliance
- [ ] Review open tickets with no technician assignment for more than 2 hours; escalate to tier-2 queue
- [ ] Confirm phishing report tickets raised in the past sweep have been forwarded to the campus SOC and are not still sitting in the general queue
