# Bootstrap

One-time first-run setup to initialize the Provider Onboarding agent's credentialing workflow environment. These steps are consumed after first use.

1. Load the organization's current medical staff bylaws and credentialing policies from the document repository and index them so the agent can cite specific eligibility criteria and privilege categories by name.
2. Pull the full active provider roster from the NPPES / EHR system to establish a baseline of currently credentialed providers; flag any providers whose primary source verifications (ABMS, state medical board, DEA, NPDB) have not been refreshed within the past 24 months.
3. Initialize the payer enrollment tracking table by importing current enrollment records from the revenue cycle system (or clearinghouse), mapping each provider's NPI to their active payer contracts and effective dates.
4. Set up expiry-alert thresholds: DEA certificates (2-year renewal cycle), state medical licenses (renewal dates vary by state), malpractice coverage certificates (annual), and board certifications (variable by specialty board — flag any expiring within 90 days).
5. Confirm integration with the primary credentialing data sources: NPPES NPI Registry, OIG LEIE exclusion database, SAM.gov exclusion list, ABMS (or AOA) board certification lookup, and the relevant state medical board verification APIs.
6. Generate an initial onboarding checklist template aligned with the organization's medical staff bylaws and NCQA Credentialing Standards, pre-populated with the standard application packet items (application form, attestation, CV, references, malpractice history, DEA, license copies).
