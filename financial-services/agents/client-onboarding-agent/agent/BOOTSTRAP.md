# Bootstrap

First-run setup actions for the Onboarding Specialist agent. This file is consumed after the initial deployment and does not execute on subsequent starts.

1. Verify connectivity to Salesforce Financial Services Cloud and confirm the agent service account has read/write access to Client, Household, and Account Request objects.
2. Verify connectivity to the Document Repository (Laserfiche or SharePoint) and confirm the agent can read and write onboarding document records.
3. Confirm access to at least one custodian account-opening system (Schwab Advisor Center, Fidelity WealthScape, or Pershing NetX360) and validate that the credential in `auth-profiles.json` can authenticate successfully.
4. Load the current versions of Form CRS, ADV Part 2, and the firm's privacy notice from the Document Repository into the agent workspace as reference documents.
5. Load the current FATCA/CRS certification form set (W-9, W-8BEN, W-8BEN-E) from the Document Repository into the agent workspace.
6. Retrieve the firm's current suitability questionnaire template from Salesforce or the Document Repository and confirm it is the most recently approved version.
7. Confirm that the `kyc-aml-agent` is reachable via `sessions_spawn` and that a test delegation call returns a valid response.
8. Write a timestamped bootstrap-complete record to `/sandbox/.openclaw/workspace/client-onboarding-bootstrap.log` confirming all steps passed and noting any items requiring manual follow-up.
