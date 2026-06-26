# 10 — AI Governance Assurance & Control Mapping Framework

> **SimulFlow S.r.l.** *(Fictional Organization)*  
> Source: 01–09 AI Governance Program Artifacts  
> Frameworks: ISO/IEC 42001 · NIST AI RMF · SOC 2 · ISO/IEC 27001 · OWASP LLM Top 10 (2025)

---

# 1. Purpose

This document provides an integrated assurance layer for SimulFlow’s AI Governance Program.

It consolidates governance artifacts, risk documentation, control frameworks, and vendor assessments into a unified **audit-ready control mapping system**.

The objective is to ensure that all AI governance activities are:

- Traceable
- Verifiable
- Mapped to recognized frameworks
- Supported by evidence
- Ready for external audit (ISO 42001 / SOC 2 / internal audit)

---

# 2. Scope

This assurance framework covers all AI systems and governance processes defined in the SimulFlow AI Governance Program, including:

- AI systems (LLMs, RAG, APIs, agentic workflows)
- AI inventory and classification
- Risk assessments and risk register
- Vendor AI services
- Governance policies and controls
- Executive reporting and roadmap planning

---

# 3. Control Mapping Model

SimulFlow adopts a **Unified Control Mapping Approach (UCMA)**:

| Layer | Description | Primary Output |
|------|-------------|----------------|
| Risk Layer | Identifies AI risks | AI Risk Register (03) |
| Control Layer | Defines mitigation controls | AI Governance Policy (07) |
| Assurance Layer | Maps controls to frameworks | This document |
| Reporting Layer | Executive visibility | Dashboard (08) |

---

# 4. Cross-Framework Control Mapping

## 4.1 Example Control Mapping Structure

| Control ID | Control Description | ISO 42001 | SOC 2 | NIST AI RMF | OWASP LLM |
|------------|--------------------|----------|--------|-------------|-----------|
| CTRL-AI-01 | Prompt Injection Protection | A.6 | CC6.1 | Measure / Manage | LLM01 |
| CTRL-AI-02 | Data Leakage Prevention | A.7 | CC6.2 | Map / Measure | LLM02 |
| CTRL-AI-03 | Vendor Risk Assessment | A.15 | CC9.2 | Govern | LLM03 |
| CTRL-AI-04 | RAG Data Integrity Controls | A.7 | CC7.1 | Measure | LLM04 |
| CTRL-AI-05 | AI Agent Authorization Controls | A.9 | CC6.1 | Manage | LLM06 |

---

# 5. Risk-to-Control Traceability

## Example Traceability Chain

| Risk ID | Risk Description | OWASP | Control ID | Evidence Location |
|----------|-----------------|--------|------------|-------------------|
| RISK-001 | Prompt Injection | LLM01 | CTRL-AI-01 | 03 Risk Register |
| RISK-002 | Sensitive Data Disclosure | LLM02 | CTRL-AI-02 | 03 Risk Register |
| RISK-003 | Data Poisoning (RAG) | LLM04 | CTRL-AI-04 | 02 Risk Assessment |
| RISK-005 | Excessive Agent Permissions | LLM06 | CTRL-AI-05 | 03 Risk Register |
| RISK-007 | Third-party AI exposure | LLM03 | CTRL-AI-03 | 06 Vendor Risk |

---

# 6. Evidence Mapping

Each control is supported by auditable evidence artifacts:

| Evidence Type | Source Document |
|---------------|-----------------|
| Risk Identification | 02-AI-Risk-Assessments |
| Risk Treatment | 03-AI-Risk-Register |
| Governance Controls | 07-AI-Governance-Policy |
| Vendor Controls | 06-Vendor-Risk-Assessment |
| Monitoring & Metrics | 08-Executive-Dashboard |
| Continuous Improvement | 09-Governance-Roadmap |

---

# 7. Audit Readiness Summary

## 7.1 Control Coverage

| Framework | Coverage |
|----------|----------|
| ISO/IEC 42001 | 85% |
| NIST AI RMF | 90% |
| SOC 2 (AI-relevant controls) | 80% |
| OWASP LLM Top 10 | 100% |

---

## 7.2 Control Effectiveness Status

| Status | Count |
|--------|------:|
| Fully Implemented | 7 |
| Partially Implemented | 4 |
| Gaps Identified | 1 |

---

## 7.3 Key Assurance Gaps

| Gap ID | Description | Priority |
|--------|-------------|----------|
| GAP-01 | AI Incident Response Framework missing | High |
| GAP-02 | Continuous AI monitoring not fully automated | High |
| GAP-03 | Vendor continuous assurance limited | Medium |

---

# 8. Audit Simulation Capability

This governance program is designed to support external audit scenarios.

## Example Audit Questions

### Q1: How do you mitigate prompt injection risks?

**Response Path:**
- Risk: RISK-001
- Control: CTRL-AI-01
- Evidence: Risk Register + Policy Section 5.1
- Framework Mapping: ISO 42001 A.6 / SOC 2 CC6.1 / OWASP LLM01

---

### Q2: How do you ensure third-party AI vendor compliance?

**Response Path:**
- Risk: RISK-007
- Control: CTRL-AI-03
- Evidence: Vendor Risk Assessment (06)
- Framework Mapping: ISO 42001 A.15 / SOC 2 CC9.2

---

### Q3: How is AI risk continuously monitored?

**Response Path:**
- Evidence: 08 Executive Dashboard
- Gap: Partial automation identified in GAP-02
- Roadmap: 09 Governance Roadmap Phase 1

---

# 9. Governance Principle

This assurance framework enforces a core principle:

> **No AI control is considered valid unless it is traceable to:**
> - A defined risk
> - A documented control
> - A mapped framework requirement
> - A verifiable evidence artifact

---

# 10. Conclusion

The SimulFlow AI Governance Program is structured as an integrated, audit-ready control system.

It provides end-to-end traceability from:

**AI system → risk → control → framework → evidence → executive reporting**

This enables consistent governance execution, regulatory alignment, and audit readiness across ISO/IEC 42001, SOC 2, and NIST AI RMF requirements.

---

*Owner: Information Security & GRC*  
*Version: 1.0*  
*Last Updated: 2026-06-26*
