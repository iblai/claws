# Tools

## ITSM Platform

- **ServiceNow** — create, update, and resolve incident tickets; search knowledge base articles; assign incidents to specialist queues; set ticket priority (P1–P4); send automated status updates to users
- **Jira Service Management / Freshservice** — alternative ITSM platforms at some institutions; equivalent incident and request management operations

## Identity & Access Management

- **Okta / Azure AD (via Graph API)** — initiate self-service password reset flow; verify account lock status; check MFA enrollment; audit recent sign-in activity (dates and locations only, no credential data); provision or de-provision application access per approved IT workflow

## Software & Licensing

- **Microsoft 365 Admin Center** — check license assignment status for M365 apps; initiate license assignment request; confirm OneDrive and Teams provisioning status
- **Software license inventory** — confirm which titles are available for student/faculty/staff download, retrieve activation key delivery instructions, check concurrent seat availability for specialized research software

## Network & Infrastructure

- **Campus Wi-Fi portal** — check device registration status, submit new device MAC address for network access, check VLAN assignment for student vs. faculty networks
- **VPN provisioning** — confirm VPN client download instructions by OS, check user's VPN group membership, initiate provisioning request

## Status & Monitoring

- **Campus status page (statuspage.io)** — check real-time operational status for email, LMS, Wi-Fi, Banner/SIS, VPN, and other critical services; retrieve active incident descriptions and estimated resolution times

## Data Sources

### Ticket & Knowledge Base

- **ServiceNow / Jira Service Management** — incident records (ticket number, category, description, priority, status, assigned group, resolution notes), knowledge base articles (symptom, resolution steps, affected systems, last verified date), problem records (root cause, known affected users, workaround), change request calendar (planned maintenance windows, affected services)

### Identity & Access

- **Okta / Azure Active Directory** — user account status (active, locked, disabled), MFA enrollment status, application assignment list, recent sign-in events (timestamp, IP, device, success/failure), group memberships; password data is never accessible or retrievable

### Device & Software Inventory

- **Jamf Pro / SCCM (Microsoft Endpoint Manager)** — managed device inventory (hostname, OS version, last check-in, patch compliance status, assigned user), software deployment status, antivirus compliance
- **Software license tracking** — licensed titles (name, vendor, version, seat count, available seats, download instructions, activation method, expiry date)

### Network

- **Campus network management (Cisco ISE / Aruba ClearPass)** — device registration status, MAC address, assigned VLAN, last seen timestamp, quarantine status (read-only; network changes require IT team action)
- **Wi-Fi infrastructure** — access point locations, SSID list (student, faculty, IoT, guest), current congestion reports

### Service Status

- **Status page** — current operational status for monitored services (email, LMS, SIS, VPN, Wi-Fi, research computing), active incident timeline, historical uptime data
