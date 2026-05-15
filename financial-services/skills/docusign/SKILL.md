---
name: docusign
description: DocuSign electronic signature platform; lets an agent send, track, and retrieve signed documents for client onboarding agreements, advisory contracts, and regulatory disclosures.
metadata: {"openclaw":{"requires":{"env":["DOCUSIGN_INTEGRATION_KEY","DOCUSIGN_SECRET_KEY","DOCUSIGN_ACCOUNT_ID","DOCUSIGN_BASE_URL","DOCUSIGN_IMPERSONATED_USER_ID"]}},"primaryEnv":"DOCUSIGN_INTEGRATION_KEY"}
---

# DocuSign

## What it is
DocuSign is the industry-standard electronic signature and agreement cloud. In financial services, it is used to collect binding client signatures on new account agreements, advisory contracts, Form CRS disclosures, FATCA certifications, and other required documents. DocuSign's audit trail and completion certificates satisfy most regulators' electronic signature requirements.

## When to use this skill
- Send a signature request envelope for a new account agreement or advisory agreement
- Track envelope status — sent, delivered, completed, declined, or expired
- Retrieve the signed document and completion certificate for recordkeeping
- Trigger FATCA re-certification reminders when a W-8 document approaches expiry
- Confirm Form CRS delivery timestamp and client acknowledgment for examination readiness
- Void or correct an envelope that was sent with errors

## Credentials
This skill authenticates using env vars declared in `metadata` above. Set them in `~/.openclaw/.env` (see `.env.example` at the config root). Required variables:
- `DOCUSIGN_INTEGRATION_KEY` - DocuSign app integration key (client ID)
- `DOCUSIGN_SECRET_KEY` - OAuth2 client secret for the integration key
- `DOCUSIGN_ACCOUNT_ID` - DocuSign account ID (GUID)
- `DOCUSIGN_BASE_URL` - REST API base URL (e.g. `https://na3.docusign.net/restapi`)
- `DOCUSIGN_IMPERSONATED_USER_ID` - User GUID for JWT impersonation (service account)

## Key operations
- `POST /v2.1/accounts/{accountId}/envelopes` — create and send a new signature envelope
- `GET /v2.1/accounts/{accountId}/envelopes/{envelopeId}` — retrieve envelope status and metadata
- `GET /v2.1/accounts/{accountId}/envelopes/{envelopeId}/documents` — list documents in an envelope
- `GET /v2.1/accounts/{accountId}/envelopes/{envelopeId}/documents/{documentId}` — download a signed document
- `PUT /v2.1/accounts/{accountId}/envelopes/{envelopeId}` — void or resend an existing envelope
- `GET /v2.1/accounts/{accountId}/envelopes?status=completed&from_date=...` — list completed envelopes by date range

## Notes
- Use the JWT Grant (service-account) OAuth2 flow for automated agent workflows; avoid password-based auth
- Demo/sandbox environment uses `https://demo.docusign.net/restapi`; production and demo credentials are separate
- Envelope creation counts against monthly plan limits; monitor usage to avoid overage charges
- Completed documents and audit trails are available for 10 years by default; confirm retention policy with your DocuSign admin
- ESIGN Act and eIDAS compliance is satisfied out of the box; verify local requirements for international signatories
