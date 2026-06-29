# 03 — AI Risk Register

> **SimulFlow S.r.l.** *(Fictional Organization)*
> Source: [01-AI-Inventory](01-AI-Inventory.md) · [02-AI-Risk-Assessments](02-AI-Risk-Assessments.md)
> Frameworks: ISO/IEC 42001 · NIST AI RMF · OWASP LLM Top 10 (2025) · ISO/IEC 27001

---

## Risk Appetite Statement

SimulFlow will not accept any unmitigated risk rated **High or Critical** involving customer data, regulatory exposure, or agentic execution capabilities. Medium risks may be accepted where the cost of mitigation exceeds the residual impact and compensating controls are in place. Low risks are accepted by default with monitoring.

| Risk Level | Default Treatment |
|------------|------------------|
| 🔴 Critical | Mitigate — mandatory, immediate priority |
| 🔴 High | Mitigate — required before next review cycle |
| 🟡 Medium | Mitigate or Accept with compensating controls |
| 🟢 Low | Accept with monitoring |

---

## Risk Register

| Risk ID | AI Asset | Risk Description | OWASP | Owner | Likelihood | Impact | Inherent Risk | Existing Controls | Treatment | Treatment Action | Due Date | Residual Risk | Status |
|---------|----------|-----------------|-------|-------|------------|--------|---------------|-------------------|-----------|-----------------|----------|---------------|--------|
| RISK-001 | AI-001 SimulFlow Assistant | Prompt Injection leading to unauthorized model behaviour | LLM01 | Product Security Manager | 4 | 5 | 🔴 Critical (20) | Prompt filtering, authentication, logging | Mitigate | Implement detection for both **direct injection** (user input) and **indirect injection** (via retrieved documents); adversarial testing before each major release | 2026-09-30 | 🔴 High (12) | In Progress |
| RISK-002 | AI-001 SimulFlow Assistant | Sensitive information disclosure through generated responses | LLM02 | Product Security Manager | 4 | 5 | 🔴 Critical (20) | Content moderation, access control | Mitigate | Deploy DLP filtering; strengthen retrieval restrictions for confidential content | 2026-08-31 | 🟡 Medium (8) | Planned |
| RISK-003 | AI-002 Knowledge Hub | Data and model poisoning of RAG knowledge sources | LLM04 | Knowledge Management Manager | 4 | 4 | 🔴 High (16) | Document approval workflow, version control | Mitigate | Introduce document integrity validation, trusted source verification, embedding anomaly detection prior to vector ingestion, and scheduled knowledge reviews | 2026-09-15 | 🟡 Medium (9) | In Progress |
| RISK-004 | AI-002 Knowledge Hub | Retrieval of unauthorized confidential documents | LLM02 | Information Security Manager | 3 | 5 | 🔴 High (15) | RBAC, Azure AD authentication | Mitigate | Implement attribute-based access control (ABAC) and periodic permission reviews | 2026-08-15 | 🟡 Medium (6) | Planned |
| RISK-005 | AI-003 Workflow Copilot | Excessive AI permissions enabling unauthorized workflow execution | LLM06 | Head of Operations | 4 | 5 | 🔴 Critical (20) | Human approval workflow, RBAC | Mitigate | Restrict automation privileges; require human approval for high-impact actions; implement tool call logging with anomaly detection for all agent-initiated actions | 2026-10-01 | 🟡 Medium (8) | In Progress |
| RISK-006 | AI-004 Developer Coding Assistant | Proprietary source code submitted to external AI services | LLM03 | Engineering Manager | 3 | 4 | 🔴 High (12) | Enterprise licensing, secure development policy | Mitigate | Implement repository classification, developer awareness training, and AI usage monitoring | 2026-09-01 | 🟡 Medium (6) | Planned |
| RISK-007 | AI-005 AI Translation API | Customer information processed by third-party AI provider without sufficient safeguards | LLM03 | Vendor Risk Manager | 3 | 4 | 🔴 High (12) | Vendor due diligence, contractual safeguards | Mitigate | Conduct annual vendor reassessment; verify GDPR compliance commitments and sub-processor controls | 2026-11-01 | 🟡 Medium (6) | Planned |
| RISK-008 | AI-006 Meeting Intelligence Assistant | Unauthorized access to meeting transcripts containing personal data | LLM02 | IT Operations Manager | 3 | 3 | 🟡 Medium (9) | Conditional Access, Microsoft Purview retention policies | Accept | Residual risk within appetite; enable sensitivity labels and quarterly access reviews as compensating controls | 2026-08-01 | 🟢 Low (4) | In Progress |
| RISK-009 | AI-001 SimulFlow Assistant | System prompt leakage exposing internal configuration and security logic | LLM07 | Product Security Manager | 3 | 4 | 🔴 High (12) | Output filtering | Mitigate | Enforce system prompt isolation; prohibit model from referencing or repeating its own instructions; conduct regular adversarial probing via jailbreak simulation | 2026-09-30 | 🟡 Medium (6) | Planned |
| RISK-010 | AI-002 Knowledge Hub | Vector and embedding manipulation enabling retrieval of unintended content | LLM08 | Knowledge Management Manager | 3 | 4 | 🔴 High (12) | Access control, source validation | Mitigate | Implement embedding anomaly detection to monitor similarity score distributions; enforce vector database access audit logging; validate retrieval outputs against expected semantic boundaries | 2026-10-15 | 🟡 Medium (6) | Planned |
| RISK-011 | AI-003 Workflow Copilot | Unbounded API consumption enabling cost explosion or service degradation | LLM10 | Head of Operations | 3 | 4 | 🔴 High (12) | None currently implemented | Mitigate | Implement API rate limiting and per-user token quotas; configure anomalous consumption alerts; enforce hard limits on agent-initiated external API call chains | 2026-09-01 | 🟡 Medium (6) | Planned |

---

## Risk Lifecycle

The following lifecycle governs all risks recorded in this register,
from initial identification through to closure or acceptance.

| Stage | Description | Responsible |
|-------|-------------|-------------|
| 🆕 New Risk | Risk identified via assessment, audit, incident, or change request | Business Owner |
| 📋 Assessment | Risk scored for likelihood, impact, and inherent risk rating | Security |
| 📝 Register | Risk formally recorded with ID, owner, and OWASP reference | GRC |
| 🔧 Treatment | Treatment option selected; mitigation actions assigned and tracked | Business Owner |
| ✅ Validation | Controls tested and evidence collected to confirm effective implementation | Security |
| 📉 Residual Review | Residual risk scored post-treatment; accepted or escalated | GRC |
| 🔄 Quarterly Review | Risk re-evaluated against current threat landscape and control effectiveness | Executive Committee |
| 🔒 Closed | Risk accepted within appetite or eliminated; documented and archived | GRC |

### Escalation Criteria

| Condition | Action |
|-----------|--------|
| Residual risk remains Critical after treatment | Escalate to Executive Committee within 5 business days |
| Treatment action overdue by 30+ days | Escalate to risk owner's line manager |
| New threat intelligence affects existing risk rating | Trigger out-of-cycle reassessment |
| AI system change or new deployment | Re-enter lifecycle at Assessment stage |


---

## Risk Treatment Summary

### Treatment Decisions

| Treatment | Count | Risk IDs |
|-----------|-------|----------|
| Mitigate | 10 | RISK-001 through RISK-007, RISK-009, RISK-010, RISK-011 |
| Accept | 1 | RISK-008 |
| Transfer | 0 | — |
| Avoid | 0 | — |

> RISK-008 accepted per risk appetite: residual risk reduced to Low (4) with compensating controls in place. No customer data or regulatory exposure at this residual level.

### Treatment Options Reference

| Option | Description |
|--------|-------------|
| Mitigate | Implement technical, administrative, or operational controls to reduce likelihood or impact |
| Accept | Risk is within organizational risk appetite; compensating controls documented |
| Transfer | Reduce exposure through contractual agreements, cyber insurance, or third-party arrangements |
| Avoid | Eliminate the activity or technology creating the unacceptable risk |

---

## Risk Metrics

### Inherent Risk Profile

| Rating | Count | Risk IDs |
|--------|-------|----------|
| 🔴 Critical (17–25) | 3 | RISK-001, RISK-002, RISK-005 |
| 🔴 High (10–16) | 8 | RISK-003, RISK-004, RISK-006, RISK-007, RISK-009, RISK-010, RISK-011 |
| 🟡 Medium (5–9) | 1 | RISK-008 |
| 🟢 Low (1–4) | 0 | — |

### Residual Risk Profile

| Rating | Count | Risk IDs |
|--------|-------|----------|
| 🔴 High (10–16) | 1 | RISK-001 |
| 🟡 Medium (5–9) | 9 | RISK-002 through RISK-007, RISK-009, RISK-010, RISK-011 |
| 🟢 Low (1–4) | 1 | RISK-008 |

### Treatment Progress

| Status | Count |
|--------|-------|
| In Progress | 4 |
| Planned | 7 |
| Completed | 0 |

---

## Risk Ownership

| Role | Responsibilities | Risks Owned |
|------|-----------------|-------------|
| Product Security Manager | Customer-facing AI services, LLM security, prompt defence | RISK-001, RISK-002, RISK-009 |
| Information Security Manager | AI governance, security controls, compliance oversight | RISK-004 |
| Knowledge Management Manager | RAG knowledge quality, document lifecycle, vector integrity | RISK-003, RISK-010 |
| Head of Operations | AI workflow automation, agent governance, resource controls | RISK-005, RISK-011 |
| Engineering Manager | Secure software development, AI coding assistant governance | RISK-006 |
| Vendor Risk Manager | Third-party AI providers, contractual assurance, GDPR | RISK-007 |
| IT Operations Manager | Collaboration platforms, identity management, access control | RISK-008 |

---

## OWASP LLM Top 10 Coverage

| OWASP ID | Risk | Covered | Risk IDs |
|----------|------|---------|----------|
| LLM01 | Prompt Injection | ✅ | RISK-001 |
| LLM02 | Sensitive Information Disclosure | ✅ | RISK-002, RISK-004, RISK-008 |
| LLM03 | Supply Chain | ✅ | RISK-006, RISK-007 |
| LLM04 | Data and Model Poisoning | ✅ | RISK-003 |
| LLM05 | Improper Output Handling | ➖ | Not in scope for this register |
| LLM06 | Excessive Agency | ✅ | RISK-005 |
| LLM07 | System Prompt Leakage | ✅ | RISK-009 |
| LLM08 | Vector and Embedding Weaknesses | ✅ | RISK-010 |
| LLM09 | Misinformation | ➖ | Not in scope for this register |
| LLM10 | Unbounded Consumption | ✅ | RISK-011 |

---

## Governance Review Cycle

| Activity | Frequency |
|----------|-----------|
| AI Risk Register Review | Quarterly |
| Critical and High Risk Review | Monthly |
| Executive Risk Reporting | Quarterly |
| Vendor Risk Reassessment | Annually |
| AI Inventory Validation | Quarterly |
| ISO/IEC 42001 Readiness Review | Annually |

---

## Appendix — AI Attack Techniques Reference

This appendix documents the AI-specific attack techniques that informed risk identification in this register. Techniques are derived from hands-on analysis of AI security vulnerabilities.

| Technique | OWASP | Affected Systems | Description |
|-----------|-------|-----------------|-------------|
| Direct Prompt Injection | LLM01 | AI-001 | Attacker crafts user input to override model instructions or extract restricted information |
| Indirect Prompt Injection via RAG | LLM01, LLM04 | AI-001, AI-002 | Malicious content embedded in retrieved documents manipulates model behaviour without direct user interaction |
| Jailbreaking | LLM01, LLM07 | AI-001 | Structured inputs bypass model safety guardrails; used to probe system prompt content and extract configuration details |
| Embedding Manipulation | LLM08 | AI-002 | Adversarially crafted documents alter vector representations in the embedding pipeline, causing retrieval of semantically incorrect content |
| Data Poisoning via Document Ingestion | LLM04 | AI-002 | Compromised or manipulated documents are introduced into the RAG knowledge base, corrupting retrieval outputs at scale |
| Excessive Agent Privilege Abuse | LLM06 | AI-003 | AI agent with overly broad permissions executes unintended or unauthorized actions across connected business systems |
| Tool Call Chain Abuse | LLM10 | AI-003 | Agent triggers unbounded sequences of API or tool calls, causing resource exhaustion, cost explosion, or downstream service disruption |
| System Prompt Extraction | LLM07 | AI-001 | Model is induced to reveal its system-level instructions through carefully structured queries or jailbreak sequences |
| Supply Chain Model Tampering | LLM03 | AI-004, AI-005 | Compromised or unverified third-party models, APIs, or datasets introduce vulnerabilities before deployment |
| Sensitive Data Leakage via API | LLM02, LLM03 | AI-004, AI-005 | Proprietary code or customer data transmitted to external AI providers is exposed through inadequate contractual or technical controls |

---

## Portfolio Linkage

| Document | How it references this register |
|----------|--------------------------------|
| [04-NIST-AI-RMF-Mapping](04-NIST-AI-RMF-Mapping.md) | Risk entries map to Govern / Map / Measure / Manage functions |
| [05-ISO42001-Gap-Assessment](05-ISO-42001-Gap-Assessment.md) | Risk treatment status informs control gap identification |
| [06-Vendor-Risk-Assessment](06-Vendor-Risk-Assessment.md) | RISK-006, RISK-007 feed directly into vendor assessment scope |
| [08-Executive-Dashboard](08-Dashboard.md) | Risk metrics and treatment progress feed leadership reporting |
| [09-Control-Improvement-Roadmap](09-Improvement-Roadmap.md) | Open risks and planned treatments inform the improvement timeline |

---

*Last updated: 2026-06-26*
