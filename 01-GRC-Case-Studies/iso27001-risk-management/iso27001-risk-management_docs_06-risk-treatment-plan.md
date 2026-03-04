# 06 — Risk Treatment Plan

[← Back to Project Overview](../README.md)

---

## Treatment Strategy

All risks scoring **≥ 20 (High/Critical)** require active treatment. The treatment plan maps identified risks to **ISO 27001 Annex A controls** and assigns governance ownership.

## Control Mapping — ISO 27001 Annex A

| Risk | Red-Zone Score | ISO 27001 Control | Control Description | Mitigation Action |
|---|---|---|---|---|
| Human Error (Phishing) | 25 | **A.6.3** — Awareness, education and training | Personnel shall receive appropriate security awareness training | Deploy enterprise-wide security awareness program with phishing simulations |
| Human Error (Misconfiguration) | 25 | **A.8.9** — Configuration management | Configurations shall be established, documented, and maintained | Implement configuration baselines and change management procedures |
| Software Attacks (TERP-Web) | 25 | **A.8.8** — Management of technical vulnerabilities | Information about technical vulnerabilities shall be obtained and evaluated | Deploy vulnerability scanning, WAF, and patch management for web applications |
| Obsolescence (AD SQL DB) | 25 | **A.8.8** — Management of technical vulnerabilities | Timely action shall be taken in response to identified vulnerabilities | Replace end-of-life Servers A and B; upgrade to current supported platforms |
| Obsolescence (TERP-Web) | 25 | **A.8.32** — Change management | Changes to information processing facilities shall be controlled | Establish formal patch management cycle for e-commerce platform |
| Info Extortion (TAS-GL) | 25 | **A.8.13** — Information backup | Backup copies shall be maintained and regularly tested | Modernize backup systems (BARS) with encryption; reduce RPO from 7 days |
| Info Extortion (AD SQL DB) | 25 | **A.8.14** — Redundancy of information processing facilities | Facilities shall be implemented with sufficient redundancy | Implement AD redundancy / failover; eliminate single point of failure |
| Access Risk (all systems) | 20 | **A.8.3** — Information access restriction | Access to information shall be restricted in accordance with access control policy | Implement role-based access control (RBAC) and periodic access reviews |
| Backup Integrity | 20 | **A.8.13** — Information backup | Backup copies shall be maintained and regularly tested | Encrypt backup data (AES-256); implement regular restore testing |
| Incident Response Gap | — | **A.5.24** — Information security incident management planning | Organization shall plan and prepare for managing incidents | Develop and test incident response plan |

## Governance Risk Ownership Model

ISO 27001 Clause 5.1 (Leadership) and Clause 9 (Performance Evaluation) require defined risk ownership and measurable oversight.

### Risk Owner Assignments

| Asset Bundle | Risk Owner | Responsibility |
|---|---|---|
| TERP-Web (E-commerce) | IT Manager + Sales Manager | Technical controls + business continuity |
| TAS-Bank (Banking Data) | CFO | Financial data protection, access authorization |
| TAS-GL (General Ledger) | CFO | Financial records integrity, backup validation |
| TAS-Pay (Payroll/PII) | HR Manager | PII protection, regulatory compliance |
| AD SQL DB (Identity) | IT Manager | Infrastructure security, redundancy |
| Fleet Logistics | Distribution Manager | Operational data protection |
| Client CRM | Sales Manager | Customer data handling |
| Enterprise Backups | IT Manager | Backup integrity, encryption, testing |

### Governance Mechanisms

To sustain risk reduction, BSI must implement:

- **Quarterly Risk Review Meetings** — Risk owners present status updates to executive leadership
- **Formal Risk Register Maintenance** — Living document updated as threats evolve or controls are implemented
- **Executive Risk Dashboard** — Summary reporting for CEO/COO/CFO with trend analysis
- **Internal Audit Alignment** — Annual internal audit against ISO 27001 controls
- **Management Review** — ISO 27001 Clause 9.3 requires top management to review the ISMS at planned intervals

---

*Previous: [← Risk Matrix](./05-risk-matrix.md) | Next: [Remediation Roadmap →](./07-remediation-roadmap.md)*
