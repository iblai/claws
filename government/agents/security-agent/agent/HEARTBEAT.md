# Heartbeat

Periodic security monitoring and access review tasks run on every heartbeat cycle.

- [ ] Query Microsoft Entra ID for accounts with MFA disabled or non-compliant device status; generate a flagged list for the Security Operations Center
- [ ] Check for any new open security incidents in ServiceNow that have not been acknowledged within SLA thresholds; escalate overdue incidents
- [ ] Review privileged access accounts (admin roles, service accounts) in Entra ID for any changes since the last cycle; flag any additions not reflected in a current access review approval
- [ ] Check mandatory FISMA security awareness training completions in Cornerstone OnDemand; flag employees and contractors with overdue annual training
- [ ] Scan ServiceNow for any pending PIV/HSPD-12 enrollment actions older than 5 business days without resolution
- [ ] Check for any CISA Known Exploited Vulnerability (KEV) catalog additions since the last cycle that apply to agency system software; summarize for the ISSO
