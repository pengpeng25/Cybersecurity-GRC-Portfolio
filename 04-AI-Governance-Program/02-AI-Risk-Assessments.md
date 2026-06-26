# 02 — AI Risk Assessments

> **SimulFlow S.r.l.** *(Fictional Organization)*
> Assessment scope: All AI systems identified in [01-AI-Inventory](../01-AI-Inventory/README.md)
> Methodology: Structured enterprise risk assessment · NIST AI RMF · OWASP LLM Top 10 (2025)

---

## Assessment Summary

| AI ID | System | Primary Threat | Inherent Risk | Residual Risk |
|-------|--------|---------------|---------------|---------------|
| AI-001 | SimulFlow Assistant | Prompt Injection | 🔴 Critical (20) | 🔴 High (12) |
| AI-002 | SimulFlow Knowledge Hub | Data Poisoning | 🔴 High (16) | 🟡 Medium (9) |
| AI-003 | SimulFlow Workflow Copilot | Excessive Agency | 🔴 Critical (20) | 🟡 Medium (8) |
| AI-004 | Developer Coding Assistant | Sensitive Information Disclosure | 🔴 High (12) | 🟡 Medium (6) |
| AI-005 | AI Translation API | Third-Party Data Exposure | 🔴 High (12) | 🟡 Medium (6) |
| AI-006 | Meeting Intelligence Assistant | Unauthorized Access to Records | 🟡 Medium (9) | 🟢 Low (4) |

> Risk treatment strategies and ownership are tracked in [03-AI-Risk-Register](../03-AI-Risk-Register/README.md)

---

## Methodology

Each system was assessed through an 8-step process:

1. AI asset identification
2. Business context analysis
3. Threat modelling (STRIDE for AI)
4. AI-specific risk identification
5. Likelihood and impact scoring
6. Existing control evaluation
7. Residual risk determination
8. Risk treatment recommendation (→ 03-AI-Risk-Register)

### Risk Scoring Matrix

**Likelihood**

| Score | Level |
|-------|-------|
| 1 | Rare |
| 2 | Unlikely |
| 3 | Possible |
| 4 | Likely |
| 5 | Almost Certain |

**Impact**

| Score | Level |
|-------|-------|
| 1 | Negligible |
| 2 | Minor |
| 3 | Moderate |
| 4 | Major |
| 5 | Severe |

**Risk Score = Likelihood × Impact**

| Score | Rating |
|-------|--------|
| 1–4 | 🟢 Low |
| 5–9 | 🟡 Medium |
| 10–16 | 🔴 High |
| 17–25 | 🔴 Critical |

---

## System Assessments

### AI-001 · SimulFlow Assistant

| Field | Detail |
|-------|--------|
| Type | Generative LLM — customer-facing |
| Threat Scenario | Attacker submits crafted prompts to override system instructions, extract confidential data, or manipulate model behaviour |
| OWASP Reference | LLM01 — Prompt Injection |
| Business Impact | Confidential data disclosure · Customer trust loss · GDPR exposure · Brand damage |

| Risk Factor | Score |
|-------------|-------|
| Likelihood | 4 — Likely |
| Impact | 5 — Severe |
| **Inherent Risk** | **🔴 Critical (20)** |

**Existing Controls**

| Control | Status |
|---------|--------|
| Prompt filtering | ✅ Implemented |
| Content moderation | ✅ Implemented |
| Output validation | ✅ Implemented |
| Authentication | ✅ Implemented |
| Audit logging | ✅ Implemented |

| **Residual Risk** | **🔴 High (12)** |
|---|---|

---

### AI-002 · SimulFlow Knowledge Hub

| Field | Detail |
|-------|--------|
| Type | RAG System — internal knowledge base |
| Threat Scenario | Malicious or compromised documents are ingested into the vector database, producing poisoned retrieval results and misleading AI-generated responses |
| OWASP Reference | LLM03 — Training Data Poisoning · LLM06 — Sensitive Information Disclosure |
| Business Impact | Incorrect business decisions · Manipulation of internal knowledge · Operational disruption |

| Risk Factor | Score |
|-------------|-------|
| Likelihood | 4 — Likely |
| Impact | 4 — Major |
| **Inherent Risk** | **🔴 High (16)** |

**Existing Controls**

| Control | Status |
|---------|--------|
| Document approval workflow | ✅ Implemented |
| Access control | ✅ Implemented |
| Source validation | ✅ Implemented |
| Version management | ✅ Implemented |
| Periodic knowledge review | ⚠️ Partial |

| **Residual Risk** | **🟡 Medium (9)** |
|---|---|

---

### AI-003 · SimulFlow Workflow Copilot

| Field | Detail |
|-------|--------|
| Type | AI Agent — workflow execution |
| Threat Scenario | Excessive permissions allow the AI agent to perform unintended or unauthorized actions, including modification of business-critical workflows |
| OWASP Reference | LLM08 — Excessive Agency |
| Business Impact | Unauthorized business transactions · Service disruption · Financial loss · Compliance violations |

> ⚠️ **Note:** Agentic systems with execution capabilities represent an elevated inherent risk profile. Likelihood is rated 4 (Likely) to reflect the frequency of misconfigured agent permissions observed in comparable enterprise deployments.

| Risk Factor | Score |
|-------------|-------|
| Likelihood | 4 — Likely |
| Impact | 5 — Severe |
| **Inherent Risk** | **🔴 Critical (20)** |

**Existing Controls**

| Control | Status |
|---------|--------|
| Human approval workflow | ✅ Implemented |
| Role-based access control | ✅ Implemented |
| Least privilege enforcement | ⚠️ Partial |
| Approval logging | ✅ Implemented |

| **Residual Risk** | **🟡 Medium (8)** |
|---|---|

---

### AI-004 · Developer Coding Assistant

| Field | Detail |
|-------|--------|
| Type | Code Generation LLM — SaaS |
| Threat Scenario | Developers inadvertently submit proprietary source code or confidential business logic to an external SaaS AI provider |
| OWASP Reference | LLM06 — Sensitive Information Disclosure · AI Supply Chain Risk |
| Business Impact | Intellectual property exposure · Source code leakage · Software supply chain risk |

> ⚠️ **Note:** Enterprise licensing and developer training reduce misuse risk but do not prevent code transmission to external infrastructure. Residual risk reflects this structural limitation.

| Risk Factor | Score |
|-------------|-------|
| Likelihood | 3 — Possible |
| Impact | 4 — Major |
| **Inherent Risk** | **🔴 High (12)** |

**Existing Controls**

| Control | Status |
|---------|--------|
| Enterprise licensing | ✅ Implemented |
| Repository access controls | ✅ Implemented |
| Secure development guidelines | ✅ Implemented |
| Developer awareness training | ⚠️ Partial |

| **Residual Risk** | **🟡 Medium (6)** |
|---|---|

---

### AI-005 · AI Translation API

| Field | Detail |
|-------|--------|
| Type | Third-Party AI API |
| Threat Scenario | Customer support tickets containing PII are processed by an external AI provider without sufficient contractual or technical safeguards |
| OWASP Reference | LLM06 — Sensitive Information Disclosure · Third-Party AI Risk |
| Business Impact | Customer data exposure · GDPR non-compliance · Third-party dependency risk |

| Risk Factor | Score |
|-------------|-------|
| Likelihood | 3 — Possible |
| Impact | 4 — Major |
| **Inherent Risk** | **🔴 High (12)** |

**Existing Controls**

| Control | Status |
|---------|--------|
| Data minimization | ✅ Implemented |
| Encryption in transit | ✅ Implemented |
| Vendor due diligence | ⚠️ Partial |
| Contractual data protection clauses | ✅ Implemented |

| **Residual Risk** | **🟡 Medium (6)** |
|---|---|

---

### AI-006 · Meeting Intelligence Assistant

| Field | Detail |
|-------|--------|
| Type | Speech-to-Text + Generative AI — Pilot |
| Threat Scenario | Meeting transcripts containing confidential or personal information become accessible to unauthorized users due to misconfigured permissions |
| OWASP Reference | LLM06 — Sensitive Information Disclosure |
| Business Impact | Privacy breaches · Confidential information disclosure · Insider risk · GDPR exposure |

> ⚠️ **Pilot Status:** Full governance controls are not yet established. This system requires priority review before broader rollout.

| Risk Factor | Score |
|-------------|-------|
| Likelihood | 3 — Possible |
| Impact | 3 — Moderate |
| **Inherent Risk** | **🟡 Medium (9)** |

**Existing Controls**

| Control | Status |
|---------|--------|
| Identity and access management | ✅ Implemented |
| Conditional access policies | ✅ Implemented |
| Retention policies | ⚠️ Partial |
| Audit logging | ✅ Implemented |

| **Residual Risk** | **🟢 Low (4)** |
|---|---|

---

## Enterprise Risk Overview

### Risk Distribution

| Rating | Systems | Count |
|--------|---------|-------|
| 🔴 Critical (Inherent) | AI-001, AI-003 | 2 |
| 🔴 High (Inherent) | AI-002, AI-004, AI-005 | 3 |
| 🟡 Medium (Inherent) | AI-006 | 1 |

### Risk Themes

| Risk Category | Affected Systems |
|---------------|-----------------|
| Prompt Injection | AI-001 |
| Data Poisoning / RAG Integrity | AI-002 |
| Excessive Agency | AI-003 |
| Sensitive Information Disclosure | AI-001, AI-004, AI-005, AI-006 |
| Third-Party AI / Supply Chain Risk | AI-004, AI-005 |
| GDPR / Privacy Exposure | AI-001, AI-005, AI-006 |

---

## Key Observations

**1. Customer-facing LLMs carry the highest inherent risk.** AI-001 reached Critical (20) due to external exposure combined with direct access to confidential content. Prompt injection remains insufficiently mitigated by content filtering alone.

**2. Agentic systems require elevated scrutiny.** AI-003 was revised to Critical (20) to reflect the structural risk profile of AI agents with execution permissions. Least privilege enforcement is only partially implemented.

**3. RAG systems introduce a distinct data integrity risk.** AI-002's poisoning risk is partially mitigated but periodic knowledge review is incomplete — a gap that directly affects the reliability of enterprise knowledge outputs.

**4. Third-party AI dependencies create a structural exposure.** AI-004 and AI-005 retain medium residual risk despite controls, because code and customer data are transmitted to external infrastructure by design. This limitation cannot be fully resolved through controls alone.

**5. AI-006 requires governance priority before rollout.** The pilot status combined with personal data processing (employee voice recordings) creates GDPR exposure that must be addressed before broader deployment.

---

## Next Steps

All identified risks are transferred to the **[03-AI-Risk-Register](../03-AI-Risk-Register/README.md)**, where each entry is assigned:

- Risk owner
- Treatment strategy (Accept / Mitigate / Transfer / Avoid)
- Mitigation actions
- Due date
- Residual risk tracking
- Review cadence

---

*Last updated: 2026-06-26 · Owner: GRC Team · Next review: 2026-09-26*
