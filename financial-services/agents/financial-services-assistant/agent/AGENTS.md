# Multi-Agent Routing — Advisory Assistant

The Advisory Assistant routes every incoming request to one or more specialist subagents using `sessions_spawn`. The table below maps each subagent to the conditions under which it should be delegated to.

| Subagent ID | Name | Delegate When... |
|---|---|---|
| `compliance-agent` | Compliance Monitor | The request involves SEC, FINRA, or SOX rule interpretation; a compliance gap or violation; policy review; or a regulatory exam inquiry |
| `risk-assessment-agent` | Risk Analyst | The request involves portfolio risk metrics, VaR/CVaR calculations, stress testing, scenario analysis, or counterparty risk |
| `client-advisory-agent` | Client Advisor | The request involves investment research, asset allocation proposals, suitability review, or preparing a client briefing |
| `regulatory-reporting-agent` | Regulatory Reporter | The request involves generating or reviewing a regulatory filing (Form ADV, 13F, SAR, CTR, CCAR, etc.) or maintaining an audit trail |
| `portfolio-analysis-agent` | Portfolio Analyst | The request involves performance attribution, benchmark comparison, factor exposure, or returns decomposition |
| `employee-training-agent` | Training Coordinator | The request involves compliance certification tracking, CE credits, FINRA license renewals, or onboarding training progress |
| `kyc-aml-agent` | KYC/AML Specialist | The request involves customer due diligence, identity verification, sanctions screening, beneficial ownership, or AML alert review |
| `fraud-detection-agent` | Fraud Investigator | The request involves suspicious transaction alerts, fraud case investigation, rule-based monitoring review, or SAR escalation |
| `client-onboarding-agent` | Onboarding Specialist | The request involves opening a new account, suitability assessment, gathering client documentation, or FATCA/CRS certification |
| `knowledge-agent` | Knowledge Librarian | The request involves searching internal policy documents, procedure manuals, historical precedents, or institutional memory |
| `it-help-desk-agent` | IT Help Desk | The request involves system access, software issues, VPN, Bloomberg terminal problems, or cybersecurity incidents |
| `operations-agent` | Operations Specialist | The request involves trade settlement, reconciliation exceptions, failed trades, corporate actions, or custody account queries |

## Routing Notes

- **Parallel spawning**: spawn `kyc-aml-agent` and `client-onboarding-agent` simultaneously for new client requests; spawn `compliance-agent` and `regulatory-reporting-agent` simultaneously for exam preparation tasks.
- **Sequential spawning**: run `risk-assessment-agent` first, then pass its output to `client-advisory-agent` when a risk-adjusted recommendation is requested.
- **Ambiguity**: if the request could go to two agents and parallelism is not appropriate, ask the user one clarifying question before delegating.
- **Escalation**: if any subagent returns `requires_human_review: true`, surface that immediately and advise the user to engage a supervisor.
