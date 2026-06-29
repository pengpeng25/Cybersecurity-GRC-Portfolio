# 10 — AI Governance Assurance & Control Mapping Framework

> **SimulFlow S.r.l.** *(Fictional Organization)*
> Source: 01–09 AI Governance Program Artifacts
> Frameworks: ISO/IEC 42001 · NIST AI RMF · SOC 2 · ISO/IEC 27001 · OWASP LLM Top 10 (2025)

---

## Purpose

This document provides an integrated assurance layer for SimulFlow's AI Governance Program. It consolidates governance artifacts, risk documentation, control frameworks, and vendor assessments into a unified audit-ready control mapping system.

The objective is to ensure that all AI governance activities are:

- Traceable from risk to control to evidence
- Verifiable against recognized frameworks
- Ready for external audit (ISO/IEC 42001 · SOC 2 · internal audit)

---

## Scope

This assurance framework covers all AI systems and governance processes defined in the SimulFlow AI Governance Program:

- AI systems: LLMs, RAG, APIs, agentic workflows, productivity AI
- AI inventory and classification
- Risk assessments and risk register
- Vendor AI services and supply chain
- Governance policies and controls
- Executive reporting and improvement planning

---

## Control Mapping Model

SimulFlow adopts a **Unified Control Mapping Approach (UCMA)** structured across four governance layers:

| Layer | Description | Primary Output |
|-------|-------------|----------------|
| Risk Layer | Identifies and scores AI risks | [03-AI-Risk-Register](03-AI-Risk-Register.md) |
| Control Layer | Defines mitigation controls and ownership | [07-AI-Governance-Policy](07-AI-Governance-Policy.md) |
| Assurance Layer | Maps controls to frameworks and evidence | This document |
| Reporting Layer | Provides executive visibility and KRIs | [08-Executive-Dashboard](08-Executive-Dashboard.md) |

---

## Cross-Framework Control Mapping

> ISO/IEC 42001 clause references are provided with titles for audit clarity.
> OWASP coverage reflects the 8 categories currently registered in [03-AI-Risk-Register](03-AI-Risk-Register.md). LLM05 and LLM09 are identified as future risks and are not yet mapped to controls.

| Control ID | Control Description | ISO/IEC 42001 | SOC 2 | NIST AI RMF | OWASP LLM |
|------------|-------------------|---------------|-------|-------------|-----------|
| CTRL-AI-01 | Prompt injection protection — direct and indirect (RAG pipeline) | A.6.2 — AI system impact assessment | CC6.1 | Measure · Manage | LLM01 |
| CTRL-AI-02 | Sensitive information disclosure prevention — DLP, output filtering, access control | A.7.4 — Data for AI systems | CC6.2 | Map · Measure | LLM02 |
| CTRL-AI-03 | Vendor risk assessment and third-party AI supply chain governance | A.5.3 — Suppliers and third parties | CC9.2 | Govern | LLM03 |
| CTRL-AI-04 | RAG data integrity — document approval, source validation, embedding anomaly detection | A.7.4 — Data for AI systems | CC7.1 | Measure | LLM04 |
| CTRL-AI-05 | AI agent authorization boundaries — least privilege, human approval, tool call logging | A.9.3 — AI system operation | CC6.1 | Manage | LLM06 |
| CTRL-AI-06 | System prompt isolation — prevent leakage of internal configuration | A.6.2 — AI system impact assessment | CC6.1 | Measure · Manage | LLM07 |
| CTRL-AI-07 | Vector database integrity — embedding anomaly detection, retrieval output validation | A.7.4 — Data for AI systems | CC7.1 | Measure | LLM08 |
| CTRL-AI-08 | API resource governance — rate limiting, token quotas, consumption alerting | A.9.3 — AI system operation | CC7.2 | Manage | LLM10 |
| CTRL-AI-09 | AI governance policy — acceptable use, prohibited behaviours, oversight requirements | A.4.1 — AI governance framework | CC1.1 | Govern | All |

---

## Risk-to-Control Traceability

| Risk ID | Risk Description | OWASP | Control ID | Evidence Location |
|---------|-----------------|-------|------------|------------------|
| RISK-001 | Prompt Injection — SimulFlow Assistant | LLM01 | CTRL-AI-01 | 03-AI-Risk-Register · 02-AI-Risk-Assessments |
| RISK-002 | Sensitive Information Disclosure — SimulFlow Assistant | LLM02 | CTRL-AI-02 | 03-AI-Risk-Register |
| RISK-003 | Data Poisoning — Knowledge Hub (RAG) | LLM04 | CTRL-AI-04 | 03-AI-Risk-Register · 02-AI-Risk-Assessments |
| RISK-004 | Unauthorized Document Retrieval — Knowledge Hub | LLM02 | CTRL-AI-02 | 03-AI-Risk-Register |
| RISK-005 | Excessive Agency — Workflow Copilot | LLM06 | CTRL-AI-05 | 03-AI-Risk-Register · 02-AI-Risk-Assessments |
| RISK-006 | Source Code Exposure — Coding Assistant | LLM03 | CTRL-AI-03 | 03-AI-Risk-Register · 06-Vendor-Risk-Assessment |
| RISK-007 | Third-Party Data Exposure — Translation API | LLM03 | CTRL-AI-03 | 03-AI-Risk-Register · 06-Vendor-Risk-Assessment |
| RISK-008 | Unauthorized Access to Meeting Records | LLM02 | CTRL-AI-02 | 03-AI-Risk-Register |
| RISK-009 | System Prompt Leakage — SimulFlow Assistant | LLM07 | CTRL-AI-06 | 03-AI-Risk-Register |
| RISK-010 | Vector and Embedding Weaknesses — Knowledge Hub | LLM08 | CTRL-AI-07 | 03-AI-Risk-Register · 02-AI-Risk-Assessments |
| RISK-011 | Unbounded API Consumption — Workflow Copilot | LLM10 | CTRL-AI-08 | 03-AI-Risk-Register |

---

## Evidence Mapping

| Evidence Type | Source Document | Evidence Form |
|---------------|----------------|---------------|
| AI system classification and ownership | 01-AI-Inventory | Structured inventory with risk ratings, lifecycle status, data classification per system |
| Risk identification and scoring | 02-AI-Risk-Assessments | Likelihood × impact matrices, threat scenarios, OWASP references per system |
| Risk treatment and ownership | 03-AI-Risk-Register | Risk register with owner, treatment option, due date, residual risk, and treatment status |
| Governance controls and acceptable use | 07-AI-Governance-Policy | Approved policy document with version control, prohibited behaviours, and control requirements |
| Vendor due diligence | 06-Vendor-Risk-Assessment | Per-vendor assessment with controls verified, open conditions, and decision rationale |
| Control gap identification | 05-ISO42001-Gap-Assessment | Gap register with current state, risk if unaddressed, and remediation target |
| Executive metrics and KRIs | 08-Executive-Dashboard | Quarterly dashboard with risk distribution, treatment progress, and KRI status |
| Improvement commitments | 09-Control-Improvement-Roadmap | Time-bound initiative plan with owners, dependencies, and success metrics |

---

## Audit Readiness Summary

### Control Coverage by Framework

| Framework | Coverage | Notes |
|-----------|:--------:|-------|
| ISO/IEC 42001 | 80% | Core governance, risk, and data controls implemented; incident response and monitoring gaps remain |
| NIST AI RMF | 90% | All four functions covered; Manage function at Level 3 pending automation |
| SOC 2 (AI-relevant controls) | 80% | CC6, CC7, CC9 controls mapped; continuous monitoring evidence pending |
| OWASP LLM Top 10 | 80% | 8 of 10 categories covered; LLM05 and LLM09 identified as future risks |

### Control Implementation Status

| Status | Count | Control IDs |
|--------|:-----:|-------------|
| ✅ Fully Implemented | 4 | CTRL-AI-02, CTRL-AI-03, CTRL-AI-05, CTRL-AI-09 |
| 🟡 Partially Implemented | 5 | CTRL-AI-01, CTRL-AI-04, CTRL-AI-06, CTRL-AI-07, CTRL-AI-08 |
| ❌ Gap | 0 | — |

### Key Assurance Gaps

| Gap ID | Description | Priority | Roadmap Phase |
|--------|-------------|----------|---------------|
| GAP-001 | AI Incident Response Playbook not yet developed | 🔴 High | Phase 1 — Q3 2026 |
| GAP-002 | Continuous AI monitoring not fully automated | 🔴 High | Phase 1 — Q3 2026 |
| GAP-003 | Vendor continuous assurance limited to onboarding | 🟡 Medium | Phase 2 — Q4 2026 |

---

## Audit Simulation

This governance program is designed to support external audit scenarios. The following examples demonstrate end-to-end traceability for common audit questions.

---

**Q1: How do you identify and mitigate prompt injection risks?**

| Step | Detail |
|------|--------|
| Risk | RISK-001 — Prompt Injection, inherent Critical (20), residual High (12) |
| Control | CTRL-AI-01 — Prompt injection protection covering direct and indirect injection via RAG pipeline |
| Evidence | 03-AI-Risk-Register (treatment status: In Progress) · 07-AI-Governance-Policy §6.1 |
| Framework | ISO/IEC 42001 A.6.2 · SOC 2 CC6.1 · NIST AI RMF Measure/Manage · OWASP LLM01 |
| Gap | Adversarial testing program in progress; full mitigation target Q3 2026 |

---

**Q2: How do you govern third-party AI vendor risk?**

| Step | Detail |
|------|--------|
| Risk | RISK-006, RISK-007 — Supply chain and third-party data exposure |
| Control | CTRL-AI-03 — Vendor risk assessment and supply chain governance |
| Evidence | 06-Vendor-Risk-Assessment (per-vendor assessments with DPA verification) · 07-AI-Governance-Policy §6.3 |
| Framework | ISO/IEC 42001 A.5.3 · SOC 2 CC9.2 · NIST AI RMF Govern · OWASP LLM03 |
| Gap | Continuous vendor monitoring pending; addressed in Phase 2 roadmap |

---

**Q3: How is AI risk continuously monitored and reported?**

| Step | Detail |
|------|--------|
| Evidence | 08-Executive-Dashboard — quarterly KRI reporting, risk trend analysis, treatment progress |
| Gap | Automated real-time monitoring not yet implemented (GAP-002) |
| Current State | Periodic manual review; KRIs tracked quarterly |
| Roadmap | 09-Control-Improvement-Roadmap Phase 1 — automated monitoring target Q3 2026 |
| Framework | NIST AI RMF Manage 4.1 · ISO/IEC 42001 §9.1 |

---

**Q4: How do you control agentic AI systems to prevent unauthorized actions?**

| Step | Detail |
|------|--------|
| Risk | RISK-005 — Excessive Agency, inherent Critical (20) |
| Control | CTRL-AI-05 — Authorization boundaries, human approval, tool call logging |
| Evidence | 03-AI-Risk-Register · 07-AI-Governance-Policy §6.4 |
| Framework | ISO/IEC 42001 A.9.3 · SOC 2 CC6.1 · NIST AI RMF Manage · OWASP LLM06 |
| Gap | Least privilege enforcement partially implemented; completion target Q4 2026 |

---

## Governance Principle

This assurance framework enforces a single core principle across all AI governance activities:

> **No AI control is considered valid unless it is traceable to:**
> 1. A defined and scored risk (03-AI-Risk-Register)
> 2. A documented control with an assigned owner (07-AI-Governance-Policy)
> 3. A mapped framework requirement (this document)
> 4. A verifiable evidence artifact (01–09 portfolio artifacts)

---

## Conclusion

The SimulFlow AI Governance Program provides end-to-end traceability across the full governance chain:

**AI System → Risk → Control → Framework → Evidence → Executive Reporting**

The program currently achieves 80% alignment with ISO/IEC 42001 and OWASP LLM Top 10, with a clear roadmap to ≥ 95% readiness by Q1 2027. All 11 registered risks are traceable to documented controls, framework mappings, and evidence artifacts, supporting consistent governance execution and audit readiness.

---

*Last updated: 2026-06-26*
