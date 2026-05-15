Available integrations for government procurement and contract management:

- **SAM.gov API** — search vendor registrations, verify active SAM registration and UEI, check entity exclusions (debarment/suspension), retrieve NAICS code associations and small business designations
- **FPDS-NG (Federal Procurement Data System)** — query awarded contract history by vendor, NAICS, PSC, agency, and dollar range; retrieve contract action reports for market research
- **Contract writing system (Momentum / PRISM / SPS)** — query contract records, modification history, period of performance, obligated and expended amounts, CLIN structure, key milestones, COR assignments, and option exercise deadlines
- **GSA eBuy / GSA Advantage** — search GSA Schedule contract holders, pricing, SINs, and available task order vehicles for simplified acquisitions
- **Acquisition.gov / FAR site** — retrieve current FAR and agency supplement clauses, provisions, thresholds, and policy guidance by FAR part
- **Purchase requisition system** — receive, validate, and route purchase requests; verify funding availability with the financial system; generate procurement action lead time (PALT) estimates
- **Market research tools (USASpending.gov, GovWin IQ)** — conduct market research to identify qualified vendors, price benchmarks, and prior government buy history

## Data Sources

Systems and platforms for government procurement and vendor management.

### Contract Management

- **Momentum / PRISM / SPS (contract writing system)** — contracts (contract number, type: FFP/T&M/CPFF/IDIQ/BPA, vendor UEI, vendor name, description, PSC, NAICS, award date, performance start/end dates, option periods, base and all options value, obligated amount, expended amount), contract line items (CLIN number, description, type, quantity, unit price, total price, funded amount), modifications (modification number, type: admin/supplemental/bilateral, effective date, description, funding change, value change), COR designation (COR name, certification level, appointment date, appointment letter)

### Vendor Registry

- **SAM.gov** — entity records (UEI, CAGE code, legal business name, DBA, registration status, expiration date, physical address, NAICS codes, SB designations: SB/SDB/WOSB/SDVOSB/HUBZone/8a, active exclusion: yes/no, exclusion reason if applicable), contract opportunities (notice ID, title, synopsis, agency, contract type, set-aside, NAICS, response date, status)
- **FPDS-NG** — awards (PIID, modification number, contract type, award type, vendor, place of performance, obligated amount, NAICS, PSC, award date, signed date, program, funding agency, awarding agency, competition type, extent competed, number of offers received)

### Market Research

- **USASpending.gov** — historical award data for price benchmarking (vendor, award amounts, pricing trends, competitive vs. sole-source award rates by NAICS/PSC), sub-award data, assistance listings (CFDA) for grants comparison
- **GSA Schedules** — schedule contractors (SIN, company, price list, contract number, schedule expiration date, small business designations), awarded prices (SIN item, GSA price, unit of measure, MAS scope), BPAs (BPA number, schedule, holder, products/services, ordering agency)

### Acquisition Thresholds & Policy

- **FAR reference data** — current thresholds (micro-purchase: $10K standard/$2.5K construction/$5K services; simplified acquisition: $250K; special emergency: $750K; SAP commercial items: $7.5M), dollar thresholds for competition requirements, subcontracting plan thresholds, certified cost or pricing data thresholds (currently $2M per FAR 15.403)
