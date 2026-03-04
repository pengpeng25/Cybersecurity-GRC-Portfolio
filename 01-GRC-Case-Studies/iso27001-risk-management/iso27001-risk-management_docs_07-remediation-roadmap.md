# 07 — 12-Month Remediation Roadmap

[← Back to Project Overview](../README.md)

---

## Roadmap Overview

The remediation plan is structured in **4 quarterly phases**, prioritizing high-frequency human risks first (quick wins), then addressing infrastructure vulnerabilities, and finally establishing sustainable governance processes.

**Projected outcome:** >40% reduction in red-zone risk exposure within 12 months.

## Phase 1: Quick Wins — People & Policy (Months 1–3)

| Initiative | Target Risk | ISO Control | Expected Impact |
|---|---|---|---|
| **Security Awareness Training** | Human Error (Score: 25) | A.6.3 | Reduce phishing susceptibility across all staff |
| **Information Security Policy** | All risks (governance gap) | A.5.1 | Establish formal security baseline and accountability |
| **Access Control Review** | Access Risk (Score: 20) | A.8.3 | Restrict access to sensitive systems based on role |

**Rationale:** Human error is the highest-frequency threat and the cheapest to address. Policy development creates the governance foundation for all subsequent controls.

## Phase 2: Infrastructure Hardening (Months 4–6)

| Initiative | Target Risk | ISO Control | Expected Impact |
|---|---|---|---|
| **Replace Servers A & B** | Obsolescence (Score: 25) | A.8.8 | Eliminate end-of-life identity infrastructure risk |
| **Patch Management Program** | Software Attacks (Score: 25) | A.8.8, A.8.32 | Systematic vulnerability remediation cycle |
| **Web Application Security** | Software Attacks on TERP-Web | A.8.8 | Deploy WAF and vulnerability scanning for e-commerce |

**Rationale:** Obsolescence is a predictable, preventable risk. Server replacement eliminates 2 red-zone scores (AD SQL DB × Obsolescence, AD SQL DB × Extortion).

## Phase 3: Resilience & Recovery (Months 7–9)

| Initiative | Target Risk | ISO Control | Expected Impact |
|---|---|---|---|
| **Backup Modernization** | Info Extortion (Score: 25) | A.8.13 | Encrypted backups, reduced RPO, tested recovery |
| **AD Redundancy** | Obsolescence × AD SQL DB | A.8.14 | Eliminate single point of failure for identity |
| **Disaster Recovery Testing** | All infrastructure risks | A.8.13, A.8.14 | Validated recovery capability |

**Rationale:** Ransomware resilience requires both prevention (Phase 1–2) and recovery capability. Backup modernization directly addresses the extortion threat.

## Phase 4: Governance & Sustainability (Months 10–12)

| Initiative | Target Risk | ISO Control | Expected Impact |
|---|---|---|---|
| **Incident Response Plan** | All threats | A.5.24 | Structured response capability for security events |
| **Internal Compliance Audit** | Governance gap | A.5.35 | Validate control effectiveness, identify remaining gaps |
| **Risk Register Formalization** | All risks | Clause 6.1 | Living risk register with quarterly review cycle |
| **Executive Dashboard** | Governance gap | Clause 9.3 | Ongoing visibility for leadership decision-making |

**Rationale:** Phase 4 transitions BSI from project-based remediation to sustainable, ongoing security governance — the foundation for potential ISO 27001 certification.

## Projected Risk Reduction

| Risk Intersection | Before | After (12 months) | Reduction |
|---|---|---|---|
| Human Error × TAS-Bank | 🔴 25 | 🟠 16 | -36% |
| Software Attacks × TERP-Web | 🔴 25 | 🟡 12 | -52% |
| Human Error × TERP-Web | 🔴 25 | 🟠 16 | -36% |
| Obsolescence × TERP-Web | 🔴 25 | 🟡 10 | -60% |
| Info Extortion × TAS-GL | 🔴 25 | 🟡 15 | -40% |
| Obsolescence × AD SQL DB | 🔴 25 | 🟢 8 | -68% |

**Average red-zone reduction: ~49%** — exceeding the 40% target.

## Beyond 12 Months: Continuous Improvement

After the initial remediation cycle, BSI should pursue:

- **ISO 27001 certification** — formal third-party audit and certification
- **ISMS scope expansion** — include regional stores and fleet systems
- **Security Operations maturity** — consider managed security services (MSSP)
- **Supply chain risk assessment** — evaluate third-party vendor security posture
- **Cyber insurance** — transfer residual risk through appropriate coverage

---

*Previous: [← Risk Treatment Plan](./06-risk-treatment-plan.md) | [Back to Project Overview →](../README.md)*
