Available integrations for government IT support:

- **ServiceNow (FedRAMP-authorized)** — create, update, and resolve incidents and service requests; search the knowledge base for known issues and approved workarounds; trigger approval workflows for access provisioning changes
- **Microsoft Entra ID / Active Directory** — look up account status, group memberships, and last sign-in; initiate supervised password-reset workflows; check MFA enrollment; read conditional access policy assignments (read-only; write actions require approval workflow)
- **Microsoft Intune / SCCM** — query device enrollment status, compliance posture, and last check-in; trigger remote diagnostics; view software deployment status
- **Agency VPN (Cisco AnyConnect / Zscaler)** — check connection status and recent authentication logs for a user; review split-tunnel policy configuration
- **Network monitoring (SolarWinds / PRTG)** — query node status and uptime; check interface throughput and recent alerts for agency network segments
- **System status dashboard** — read planned maintenance windows, active outages, and degraded services from the agency IT status board
- **Change management calendar** — verify approved maintenance windows before recommending system changes; submit emergency change requests for CAB review

## Data Sources

Systems and platforms for government IT support operations.

### IT Service Management

- **ServiceNow (FedRAMP High)** — incidents (incident number, category, subcategory, priority: P1-P4, state, opened by, assigned group, assigned to, short description, work notes, resolution code, SLA breach flag, CMDB CI), service requests (RITM number, catalog item, requested for, approval status, fulfillment group, SLA target), change records (change number, type: standard/normal/emergency, risk, schedule, CAB approval status, implementation notes), knowledge articles (article ID, title, category, content, linked incidents, view count, rating)

### Identity & Access

- **Microsoft Entra ID** — user objects (UPN, display name, department, job title, account enabled, last sign-in, MFA status, license assignments, group memberships, conditional access policy matches), password policy (expiration, complexity, lockout threshold), self-service password reset (SSPR enrollment status, registered methods)
- **On-premises Active Directory** — accounts (sAMAccountName, OU path, account status, lockout status, password last set, logon hours), group policy objects (GPO name, linked OUs, key settings), privileged access (admin group membership, Tier 0/1/2 designation)

### Endpoint Management

- **Microsoft Intune** — device records (device name, OS version, last check-in, compliance status, enrollment type, primary user, BitLocker encryption status), software deployment status (app name, version, install result), non-compliance reasons

### Network & VPN

- **Cisco AnyConnect / Zscaler ZIA** — VPN session logs (user, client IP, assigned tunnel IP, gateway, connect time, disconnect time, bytes transferred, authentication result), policy profiles (split tunnel config, allowed/blocked network segments)
- **SolarWinds NPM** — node status (name, IP, status: up/down, response time, CPU/memory utilization), interface statistics (bandwidth in/out, utilization %, errors, discards), recent alerts (alert name, trigger condition, node, timestamp, acknowledgment status)

### Change & Asset

- **Change management calendar** — change windows (window name, start/end datetime, affected systems, authorized change types, CAB approval status, emergency contact)
- **CMDB** — configuration items (CI name, class: server/workstation/network device/application, status, owner, location, OS, serial number, last audit date, relationships to other CIs, linked incidents)
