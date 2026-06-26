# 06 — Vendor Risk Assessment

> **SimulFlow S.r.l.** *(Fictional Organization)*
> Source: [01-AI-Inventory](../01-AI-Inventory/README.md) · [03-AI-Risk-Register](../03-AI-Risk-Register/README.md)
> Frameworks: ISO/IEC 42001 · ISO/IEC 27001 · NIST AI RMF · SOC 2

---

## Purpose

This document presents a structured third-party AI vendor risk assessment for SimulFlow, evaluating the security, privacy, governance, and operational risks associated with external AI providers across onboarding and the full vendor lifecycle.

The assessment supports:

- Third-party due diligence
- AI supply chain governance
- Vendor risk treatment
- Procurement decision-making
- Continuous monitoring

---

## Vendor Risk Management Lifecycle

| Stage | Description | Responsible |
|-------|-------------|-------------|
| 🔍 Vendor Identification | New AI vendor proposed by business unit | Business Owner |
| 📊 Criticality Assessment | Business impact and data sensitivity evaluated | GRC |
| 🔎 Security Due Diligence | Security, privacy, and AI governance reviewed | Security |
| 📋 Risk Assessment | Risks scored and treatment options determined | GRC |
| ✅ Approval / Rejection | Vendor approved, conditionally approved, or rejected | GRC + Legal |
| 📄 Contract and Controls | DPA, security requirements, and audit rights established | Legal |
| 📡 Continuous Monitoring | Ongoing vendor security posture tracked | Security |
| 🔄 Annual Reassessment | Full reassessment conducted annually or on trigger events | GRC |

---

## Vendor Inventory

| Vendor | Service | AI System | Criticality | Data Classification |
|--------|---------|-----------|-------------|---------------------|
| Azure OpenAI | Enterprise LLM | AI-001 SimulFlow Assistant | 🔴 High | Confidential |
| Azure AI Search | Vector Database + RAG | AI-002 Knowledge Hub | 🔴 High | Confidential — Internal |
| GitHub Copilot Enterprise | AI Coding Assistant | AI-004 Developer Coding Assistant | 🟡 Medium | Confidential |
| DeepL API | AI Translation | AI-005 AI Translation API | 🟡 Medium | Confidential — contains Personal Data |

---

## Vendor Assessment Summary

> **Overall Risk** reflects residual exposure after vendor-provided controls are considered, not inherent risk. Vendors with strong security certifications and contractual safeguards receive a lower overall risk rating than their individual domain scores may suggest.

| Vendor | Governance | Security | Privacy | AI Supply Chain | Overall Risk | Decision |
|--------|------------|----------|---------|-----------------|--------------|----------|
| Azure OpenAI | ✅ High | ✅ High | ✅ High | 🟡 Medium | 🟡 Medium | Approved |
| Azure AI Search | ✅ High | ✅ High | 🟡 Medium | 🟡 Medium | 🟡 Medium | Approved with Conditions |
| GitHub Copilot Enterprise | ✅ High | ✅ High | 🟡 Medium | 🟡 Medium | 🟡 Medium | Approved |
| DeepL API | 🟡 Medium | 🟡 Medium | ✅ High | 🟢 Low | 🟡 Medium | Approved with Monitoring |

---

## Detailed Assessments

### Azure OpenAI

| Field | Detail |
|-------|--------|
| Business Purpose | Enterprise LLM powering the customer-facing SimulFlow Assistant |
| AI System | AI-001 |
| Related Risks | RISK-001, RISK-002, RISK-009 |

**Key Risks**

| Risk | OWASP | Notes |
|------|-------|-------|
| Prompt injection via crafted user input | LLM01 | External-facing deployment increases exposure |
| Sensitive information disclosure | LLM02 | Customer data processed in LLM context window |
| Supply chain: model update introducing behaviour changes | LLM03 | Microsoft controls model versioning; change notification required |
| Poisoned pre-trained weights from upstream training data | LLM04 | Risk inherent to foundation model supply chain |
| Vendor service outage | — | High criticality system; SLA monitoring required |

**Vendor-Provided Controls**

| Control | Status |
|---------|--------|
| Enterprise authentication (Azure AD) | ✅ Verified |
| Encryption in transit and at rest | ✅ Verified |
| Regional EU deployment (Azure EU West) | ✅ Verified |
| Audit logging | ✅ Verified |
| ISO 27001 / SOC 2 certification | ✅ Verified |
| Microsoft EU Data Boundary | ✅ Verified |

**SimulFlow Required Controls**

| Control | Status |
|---------|--------|
| Prompt filtering and output validation | ✅ Implemented |
| Human review for high-impact outputs | ✅ Implemented |
| API monitoring and token consumption alerts | ✅ Implemented |
| System prompt isolation | 🟡 In Progress |

**Assessment Outcome:** ✅ Approved — residual vendor risk acceptable with compensating controls in place.

---

### Azure AI Search

| Field | Detail |
|-------|--------|
| Business Purpose | Vector database and retrieval engine supporting the RAG-based SimulFlow Knowledge Hub |
| AI System | AI-002 |
| Related Risks | RISK-003, RISK-010 |

**Key Risks**

| Risk | OWASP | Notes |
|------|-------|-------|
| Embedding manipulation altering retrieval results | LLM08 | Core risk for vector database deployments |
| Unauthorized retrieval of confidential documents | LLM02 | Access control misconfiguration risk |
| Data residency and sovereignty concerns | — | Must confirm EU data boundary compliance |
| Dependency confusion via third-party index plugins | LLM03 | Supply chain risk for Azure AI Search extensions |

**Vendor-Provided Controls**

| Control | Status |
|---------|--------|
| Encryption in transit and at rest | ✅ Verified |
| Azure AD integration and RBAC | ✅ Verified |
| ISO 27001 / SOC 2 certification | ✅ Verified |
| EU data residency | ✅ Verified |
| Audit logging | ✅ Verified |
| Annual penetration testing | 🟡 Evidence requested — pending |

**SimulFlow Required Controls**

| Control | Status |
|---------|--------|
| Document approval workflow before vector ingestion | ✅ Implemented |
| Embedding anomaly detection | 🟡 In Progress |
| Quarterly access review | 🟡 Planned |
| Backup and recovery validation | 🟡 Planned |

**Assessment Outcome:** 🟡 Approved with Conditions — annual penetration testing evidence and EU data boundary confirmation required within 60 days.

---

### GitHub Copilot Enterprise

| Field | Detail |
|-------|--------|
| Business Purpose | AI coding assistant supporting software development teams |
| AI System | AI-004 |
| Related Risks | RISK-006 |

**Key Risks**

| Risk | OWASP | Notes |
|------|-------|-------|
| Proprietary source code transmitted to external SaaS | LLM02 | Structural risk; cannot be fully mitigated by controls |
| AI-generated insecure or vulnerable code | LLM05 | Output handling risk; requires secure code review |
| Supply chain: compromised model update or plugin | LLM03 | Dependency confusion risk via GitHub Marketplace extensions |
| Poisoned code suggestions from training data | LLM04 | Foundation model training data governance is opaque |

**Vendor-Provided Controls**

| Control | Status |
|---------|--------|
| Enterprise licensing with data isolation | ✅ Verified |
| No training on customer code (Enterprise tier) | ✅ Verified |
| ISO 27001 / SOC 2 certification | ✅ Verified |
| Audit logging | ✅ Verified |
| GitHub Advanced Security integration | ✅ Verified |

**SimulFlow Required Controls**

| Control | Status |
|---------|--------|
| Repository classification policy | 🟡 In Progress |
| Secure AI coding guidelines | ✅ Implemented |
| Developer awareness training | 🟡 In Progress |
| AI-generated code review requirement | ✅ Implemented |

**Assessment Outcome:** ✅ Approved — note structural limitation: source code transmission to external infrastructure cannot be eliminated by controls alone. Residual risk accepted per Risk Appetite Statement.

---

### DeepL API

| Field | Detail |
|-------|--------|
| Business Purpose | Translation of multilingual customer support communications |
| AI System | AI-005 |
| Related Risks | RISK-007 |

**Key Risks**

| Risk | OWASP | Notes |
|------|-------|-------|
| Customer personal data processed by third-party AI | LLM02 | GDPR Article 28 obligations apply |
| Data retention by vendor beyond agreed period | — | DPA must specify deletion obligations |
| Subprocessor changes introducing new data flows | LLM03 | Subprocessor list must be monitored |
| Limited AI governance transparency | LLM03 | Model provenance and training data not publicly disclosed |

**Vendor-Provided Controls**

| Control | Status |
|---------|--------|
| GDPR compliance and EU data processing | ✅ Verified |
| Data Processing Agreement (DPA) in place | ✅ Verified |
| Encryption in transit | ✅ Verified |
| No training on customer data (API tier) | ✅ Verified |
| ISO 27001 certification | ✅ Verified |
| Subprocessor list published | 🟡 Reviewed — monitoring required |

**SimulFlow Required Controls**

| Control | Status |
|---------|--------|
| Data minimization before API submission | ✅ Implemented |
| Annual privacy and DPA review | 🟡 Planned |
| Subprocessor change notification process | 🟡 Planned |
| PII redaction for sensitive tickets | 🟡 In Progress |

**Assessment Outcome:** 🟡 Approved with Monitoring — annual GDPR compliance review and subprocessor monitoring required.

---

## High-Risk Indicators

The following conditions require escalation and additional review before vendor approval:

| Indicator | Risk Level |
|-----------|------------|
| No documented AI governance program | 🔴 High |
| No GDPR compliance documentation | 🔴 High |
| No security certifications (ISO 27001 / SOC 2) | 🔴 High |
| No incident response process | 🔴 High |
| Unknown model provenance or training data sources | 🔴 High |
| No customer audit rights | 🔴 High |
| Undocumented subprocessors | 🔴 High |
| No encryption for data at rest | 🔴 Critical |
| Data processing outside EU without adequate safeguards | 🔴 Critical |

---

## Vendor Due Diligence Checklist

| Assessment Item | Azure OpenAI | Azure AI Search | GitHub Copilot | DeepL API |
|----------------|:------------:|:---------------:|:--------------:|:---------:|
| Security certifications reviewed | ✅ | ✅ | ✅ | ✅ |
| GDPR documentation verified | ✅ | ✅ | ✅ | ✅ |
| Data Processing Agreement signed | ✅ | ✅ | ✅ | ✅ |
| Subprocessors identified | ✅ | ✅ | ✅ | 🟡 |
| AI governance documentation reviewed | ✅ | ✅ | ✅ | 🟡 |
| Incident response capability verified | ✅ | 🟡 | ✅ | 🟡 |
| Business continuity and SLA reviewed | ✅ | ✅ | ✅ | ✅ |
| Annual penetration testing evidence | ✅ | 🟡 | ✅ | 🟡 |
| Risk owner assigned | ✅ | ✅ | ✅ | ✅ |

---

## Continuous Monitoring

Vendors are reassessed annually or when any of the following trigger events occur:

| Trigger | Action |
|---------|--------|
| Major AI model update | Out-of-cycle risk review |
| New or changed subprocessors | Privacy impact assessment |
| Security incident at vendor | Immediate escalation to GRC |
| Regulatory changes affecting data processing | Legal and GRC review |
| Significant contract modification | Full reassessment |
| Material change in vendor business operations | Criticality reassessment |

---

## Vendor Risk Metrics

| Metric | Value |
|--------|-------|
| Vendors Assessed | 4 |
| High Criticality Vendors | 2 |
| Approved | 2 |
| Approved with Conditions | 1 |
| Approved with Monitoring | 1 |
| Rejected | 0 |
| Annual Reviews Scheduled | 4 |
| Open Conditions | 2 |

---

## Relationship to AI Risk Register

| Vendor | AI System | Related Risk IDs |
|--------|-----------|-----------------|
| Azure OpenAI | AI-001 | RISK-001, RISK-002, RISK-009 |
| Azure AI Search | AI-002 | RISK-003, RISK-010 |
| GitHub Copilot Enterprise | AI-004 | RISK-006 |
| DeepL API | AI-005 | RISK-007 |

---

## Improvement Opportunities

| Priority | Recommendation |
|----------|---------------|
| 🔴 High | Implement continuous vendor security monitoring |
| 🔴 High | Define and document AI vendor onboarding workflow |
| 🟡 Medium | Standardize AI-specific vendor security questionnaire |
| 🟡 Medium | Integrate vendor reassessments into quarterly governance reviews |
| 🟢 Low | Automate vendor evidence collection and tracking |

---

*Last updated: 2026-06-26 · Owner: Vendor Risk Manager · Next review: 2026-09-26*
