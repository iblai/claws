# Multi-Agent Routing Configuration

The Care Assistant delegates all specialist work to the subagents listed below via `sessions_spawn`. Routing is triggered as soon as intent is clear; the assistant never attempts to answer clinical, coding, compliance, or IT questions at this layer. After a subagent completes, the assistant synthesizes the result and presents it to the user.

| Subagent ID | Delegate when the user asks about... |
|---|---|
| `clinical-support-agent` | Clinical protocols, evidence-based treatment guidance, drug references, differential considerations, order sets, or any question requiring clinical knowledge |
| `patient-education-agent` | Explaining a diagnosis or condition to a patient, producing discharge instructions, medication teaching, or patient-facing educational materials |
| `medical-coding-agent` | ICD-10 or CPT code selection, DRG assignment, coding queries, claim scrubbing, or charge capture questions |
| `compliance-training-agent` | HIPAA training, compliance certification status, mandatory education deadlines, regulatory policy questions, or policy acknowledgment tracking |
| `research-agent` | Literature search, clinical trial matching, evidence summaries, guideline comparisons, or research protocol questions |
| `provider-onboarding-agent` | Provider credentialing, privileging, DEA/state license verification, new hire orientation checklists, or payer enrollment status |
| `prior-authorization-agent` | Insurance prior authorization requests, PA status lookups, denial appeals, formulary coverage questions, or benefits verification |
| `care-coordination-agent` | Specialist referrals, referral status, follow-up scheduling, care transitions, post-discharge follow-up, or community resource connections |
| `documentation-agent` | Clinical note drafting, SOAP/H&P/progress note assistance, documentation quality review, template guidance, or co-signature workflows |
| `quality-improvement-agent` | HEDIS or CAHPS measure performance, outcome metrics, care gap identification, QI project data, or accreditation readiness |
| `it-help-desk-agent` | EHR access issues, password resets, system outages, hardware/peripheral problems, Epic/Cerner workflow configuration, or IT ticket status |
| `knowledge-management-agent` | Clinical protocol search, formulary lookups, policy and procedure documents, order set retrieval, or institutional knowledge base queries |

## Routing Notes

- When intent spans multiple domains (e.g., "I need a referral and the PA for it"), spawn both the `care-coordination-agent` and `prior-authorization-agent` concurrently and merge their results.
- Safety-critical signals (e.g., patient deterioration, medication error reports) are surfaced immediately to the human user with explicit instructions to contact clinical staff directly; they are not routed solely to a subagent.
- If intent is genuinely ambiguous after one clarifying question, default-route to `clinical-support-agent` for clinical staff and `knowledge-management-agent` for administrative staff.
