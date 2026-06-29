# 05 — ISO/IEC 42001 Gap Assessment

> **SimulFlow S.r.l.** *(Fictional Organization)*
> Source: [01-AI-Inventory](01-AI-Inventory.md) · [02-AI-Risk-Assessments](02-AI-Risk-Assessments.md) · [03-AI-Risk-Register](03-AI-Risk-Register.md) · [04-NIST-AI-RMF-Mapping](04-NIST-AI-RMF-Mapping.md)
> Framework: ISO/IEC 42001:2023 Artificial Intelligence Management System (AIMS)

---

## Purpose

This document evaluates SimulFlow's AI Governance Program against selected requirements of ISO/IEC 42001:2023. The assessment identifies governance strengths, control gaps, and improvement opportunities to support future implementation of an Artificial Intelligence Management System (AIMS).

This is a readiness review, not a certification audit.

---

## Assessment Methodology

| Status | Meaning |
|--------|---------|
| ✅ Implemented | Requirement fully addressed with documented evidence |
| 🟡 Partial | Controls exist but require improvement |
| ❌ Gap | Control not yet implemented |

---

## Assessment Summary

| Domain | Status | Notes |
|--------|--------|-------|
| AI Governance Structure | ✅ | Roles, ownership, and policy established |
| AI Inventory | ✅ | Enterprise inventory with classification complete |
| Risk Management | ✅ | Structured assessment methodology operational |
| Risk Treatment | ✅ | Treatment plans with ownership and due dates tracked |
| Third-Party AI | 🟡 | Onboarding assessment exists; continuous monitoring pending |
| AI Monitoring | 🟡 | Metrics defined; automated monitoring not yet implemented |
| AI Incident Management | ❌ | No AI-specific incident response procedures |
| Continuous Improvement | 🟡 | Improvement roadmap documented; not yet operationalized |

**Overall Readiness: High — ~80% alignment to selected ISO/IEC 42001 objectives**

---

## Control Assessment

| ISO/IEC 42001 Requirement | Portfolio Evidence | Status | Comments |
|--------------------------|-------------------|--------|----------|
| AI Governance Structure | 07-AI-Governance-Policy | ✅ | Governance roles and accountability defined |
| AI Inventory | 01-AI-Inventory | ✅ | Enterprise AI inventory established with lifecycle status |
| AI Risk Assessment | 02-AI-Risk-Assessments | ✅ | Structured methodology with likelihood, impact, and residual risk |
| AI Risk Register | 03-AI-Risk-Register | ✅ | Risk ownership, treatment plans, and review cycle documented |
| Risk Treatment Process | 03-AI-Risk-Register | ✅ | Treatment decisions governed by Risk Appetite Statement |
| AI Roles and Responsibilities | 07-AI-Governance-Policy | ✅ | Ownership assigned per AI system and risk entry |
| Third-Party AI Governance | 06-Vendor-Risk-Assessment | 🟡 | Assessment process established; continuous reassessment not yet implemented |
| Data Governance | 01-AI-Inventory | ✅ | Data classification scheme applied across all AI systems |
| AI Lifecycle Governance | 01-AI-Inventory + 02 | 🟡 | Deployed systems covered; formal lifecycle checkpoints not yet defined |
| AI Monitoring | 08-Executive-Dashboard | 🟡 | Governance metrics defined; continuous automated monitoring pending |
| AI Incident Management | — | ❌ | AI-specific incident response procedures not yet developed |
| Continuous Improvement | 09-Control-Improvement-Roadmap | 🟡 | Improvement planning documented; operationalization in progress |

---

## Threat-to-Control Mapping

> This mapping covers the full OWASP LLM Top 10 (2025) threat landscape as a governance reference.
> LLM05 and LLM09 are included here as potential control gaps even though they are not currently recorded in the AI Risk Register. See [03-AI-Risk-Register — OWASP Coverage](../03-AI-Risk-Register/README.md) for scope rationale.

| OWASP ID | Threat | Primary Control | Status |
|----------|--------|----------------|--------|
| LLM01 | Prompt Injection | Prompt validation, adversarial testing | 🟡 Partial |
| LLM02 | Sensitive Information Disclosure | Data classification, DLP, access control | ✅ Implemented |
| LLM03 | Supply Chain | Vendor risk assessment, contractual controls | 🟡 Partial |
| LLM04 | Data and Model Poisoning | Document approval, source validation, embedding anomaly detection | 🟡 Partial |
| LLM05 | Improper Output Handling | Output validation | 🟡 Partial — not in Risk Register; identified as potential future risk |
| LLM06 | Excessive Agency | Human approval workflow, RBAC, tool call logging | ✅ Implemented |
| LLM07 | System Prompt Leakage | Prompt isolation, adversarial probing | 🟡 Partial |
| LLM08 | Vector and Embedding Weaknesses | Embedding anomaly detection, vector DB audit logging | 🟡 Partial |
| LLM09 | Misinformation | Human review, content governance | 🟡 Partial — not in Risk Register; identified as potential future risk |
| LLM10 | Unbounded Consumption | API rate limiting, token quotas, consumption alerts | 🟡 Partial |

---

## Control Gaps

| Gap ID | Gap | Current State | Risk if Unaddressed | Recommendation | Priority | Target |
|--------|-----|--------------|---------------------|----------------|----------|--------|
| GAP-001 | AI Incident Response | No AI-specific incident response process exists | Delayed detection and containment of prompt injection, model compromise, or AI misuse | Develop AI Incident Response Playbook integrated with enterprise Security Incident Response Plan | 🔴 High | Q3 2026 |
| GAP-002 | Continuous AI Monitoring | AI metrics reviewed periodically; no automated monitoring | Delayed detection of abnormal AI behaviour, model abuse, or guardrail failures | Implement automated monitoring for prompt injection attempts, token consumption anomalies, retrieval failures, and failed guardrails | 🔴 High | Q3 2026 |
| GAP-003 | AI Supply Chain Assurance | Vendor assessments performed at onboarding only | Changes to third-party models or APIs may introduce undetected risks | Implement annual reassessments and continuous monitoring signals for critical AI vendors | 🟡 Medium | Q4 2026 |
| GAP-004 | AI Model Lifecycle Governance | Inventory captures deployed systems; formal lifecycle checkpoints not defined | Models may be updated or retired without governance approval | Establish governance checkpoints for design approval, risk assessment, deployment, major updates, and decommissioning | 🟡 Medium | Q4 2026 |

---

## Readiness Roadmap

| Phase | Timeline | Priority Activities |
|-------|----------|-------------------|
| Phase 1 | Q3 2026 | AI Incident Response Playbook |
| Phase 1 | Q3 2026 | Continuous AI Monitoring Implementation |
| Phase 2 | Q4 2026 | Vendor Continuous Assurance Program |
| Phase 2 | Q4 2026 | AI Lifecycle Governance Checkpoints |
| Phase 3 | Q1 2027 | AI Governance Committee Establishment |
| Phase 3 | Q1 2027 | AI Control Automation |


---

## Conclusion

SimulFlow's AI Governance Program demonstrates a mature governance foundation aligned with ISO/IEC 42001. Core capabilities — including AI inventory management, structured risk assessment, risk treatment tracking, and governance oversight — are established and provide a strong basis for a future AIMS implementation.

The highest-priority improvements are AI incident response procedures and continuous monitoring capabilities. When addressed, these gaps would bring overall readiness to approximately **95% alignment** with the selected ISO/IEC 42001 objectives.

**Overall readiness: High — ~80% alignment**

---

*Last updated: 2026-06-26*
