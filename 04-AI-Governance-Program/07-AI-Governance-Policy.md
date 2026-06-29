# 07 — AI Governance Policy

> **SimulFlow S.r.l.** *(Fictional Organization)*
> Source: [01-AI-Inventory](01-AI-Inventory.md) · [03-AI-Risk-Register](03-AI-Risk-Register.md) · [05-ISO42001-Gap-Assessment](05-ISO42001-Gap-Assessment.md)
> Frameworks: ISO/IEC 42001 · ISO/IEC 27001 · NIST AI RMF · OWASP LLM Top 10 (2025)

---


## 1. Purpose

This policy defines the governance principles, requirements, and control expectations for the development, deployment, and use of Artificial Intelligence (AI) systems within SimulFlow S.r.l.

The objective is to ensure that AI systems are:

- Secure by design
- Compliant with applicable regulations
- Transparent and explainable where feasible
- Aligned with business objectives and risk appetite
- Continuously monitored and improved

---

## 2. Scope

This policy applies to:

- All AI/ML systems developed internally
- Third-party AI services (LLMs, APIs, SaaS AI tools)
- RAG systems and vector databases
- AI agents and workflow automation systems
- AI-assisted development tools

This policy applies to all employees, contractors, and third parties who develop, deploy, configure, or use AI systems on behalf of SimulFlow.

---

## 3. Governance Principles

SimulFlow AI governance is based on the following principles:

| Principle | Description | Framework Reference |
|-----------|-------------|-------------------|
| Accountability | Every AI system must have a defined business owner responsible for risk and compliance | ISO 42001 §5.3 |
| Transparency | AI usage must be documented, traceable, and auditable | ISO 42001 §7.5 |
| Security by Design | Security controls must be implemented during the design phase, not retrofitted | NIST AI RMF — Govern 1.2 |
| Data Minimization | Only data necessary for the stated business purpose may be processed by AI systems | GDPR Article 5(1)(c) |
| Human Oversight | High-impact AI decisions require human review and approval before execution | NIST AI RMF — Govern 1.1 |
| Risk-Based Approach | Controls are proportionate to the risk level of each AI system | ISO 42001 §6.1 |
| Continuous Monitoring | AI systems must be continuously assessed against evolving threat and regulatory landscapes | NIST AI RMF — Manage 4.1 |

---

## 4. AI System Classification

All AI systems must be classified prior to production deployment. Classification is based on **risk level and business impact**, not audience alone.

| Tier | Risk Level | Description | Examples |
|------|------------|-------------|---------|
| Tier 1 | 🔴 High / Critical | Customer-facing AI, agentic systems with execution capabilities, systems processing sensitive or personal data at scale | SimulFlow Assistant (AI-001), Workflow Copilot (AI-003) |
| Tier 2 | 🟡 Medium | Internal productivity AI, code generation tools, systems with limited external exposure | Developer Coding Assistant (AI-004), AI Translation API (AI-005) |
| Tier 3 | 🟢 Low | Support tools, pilot systems, AI with human-in-the-loop and no sensitive data processing | Meeting Intelligence Assistant (AI-006) |

Tier classification determines:

- Approval workflow and sign-off authority
- Risk assessment depth and frequency
- Monitoring and alerting requirements
- Acceptable use restrictions

---

## 5. Acceptable Use and Prohibited Behaviours

### 5.1 Acceptable Use

Users may interact with approved AI systems for legitimate business purposes within the boundaries defined in the AI Inventory and this policy.

### 5.2 Prohibited Behaviours

The following behaviours are strictly prohibited for all users:

| Prohibited Action | Risk | OWASP Reference |
|------------------|------|-----------------|
| Attempting to extract or expose system prompt instructions | System configuration leakage | LLM07 |
| Using crafted inputs to bypass content filters or safety controls (jailbreaking) | Safety control circumvention | LLM01 |
| Submitting unclassified or restricted data into AI systems without authorization | Sensitive data exposure | LLM02 |
| Attempting to manipulate AI model behaviour through adversarial prompt sequences | Prompt injection | LLM01 |
| Using AI-generated outputs for high-risk decisions without human review | Excessive reliance on AI | LLM06 |
| Uploading malicious or manipulated documents into RAG knowledge systems | Data poisoning | LLM04 |
| Circumventing API rate limits or resource consumption controls | Unbounded consumption | LLM10 |

Violations of these prohibitions must be reported to the GRC team and may result in disciplinary action.

---

## 6. Mandatory Control Requirements

### 6.1 Security Controls

- Prompt injection protections must be implemented for all LLM systems, covering both direct injection (user input) and indirect injection (via retrieved documents in RAG pipelines)
- Sensitive data must not be exposed via model outputs
- Output filtering must be applied to all customer-facing AI systems
- AI systems must follow least privilege access principles
- System prompts must be isolated and must not be reproducible or referenceable by the model in any output

### 6.2 Data Protection

- Personal data must not be used for model training without a valid legal basis under GDPR
- Data classification must be enforced throughout AI pipelines
- Retention periods must be defined for AI-generated content
- Cross-border data transfers must comply with GDPR Chapter V requirements

### 6.3 Third-Party AI Controls

- All AI vendors must undergo Vendor Risk Assessment before onboarding (see [06-Vendor-Risk-Assessment](06-Vendor-Risk-Assessment.md))
- Data Processing Agreements (DPA) must be signed before any personal data is transmitted to a third-party AI provider
- Model provenance must be documented where available
- Vendors must be reassessed annually or upon trigger events defined in the Vendor Risk Management Lifecycle

### 6.4 AI Agent Controls

- All agentic systems must operate within explicit, documented authorization boundaries
- High-impact actions (financial transactions, workflow modifications, external communications) require human approval before execution
- All tool calls and agent-initiated API requests must be logged and monitored
- API usage must be rate-limited and token consumption must be subject to hard limits and alerting thresholds

### 6.5 RAG and Vector Database Controls

- All documents must pass an approval workflow before ingestion into vector databases
- Embedding anomaly detection must be implemented to identify manipulated or poisoned content
- Retrieval outputs must be validated against expected semantic boundaries
- Vector database access must be subject to audit logging and periodic access reviews

---

## 7. Risk Management Integration

This policy is directly enforced through:

| Document | Role |
|----------|------|
| [03-AI-Risk-Register](../03-AI-Risk-Register/README.md) | Tracks risk ownership, treatment, and residual risk |
| [06-Vendor-Risk-Assessment](../06-Vendor-Risk-Assessment/README.md) | Governs third-party AI onboarding and monitoring |
| [05-ISO42001-Gap-Assessment](../05-ISO42001-Gap-Assessment/README.md) | Identifies control gaps and improvement priorities |

No AI system may be deployed without:

- Completed risk assessment
- Risk acceptance or mitigation approval from the GRC team
- Control mapping verification against this policy

---

## 8. AI Security Incident Reporting

Any suspected AI security incident — including prompt injection attempts, unauthorized data disclosure, model misuse, or jailbreaking — must be reported to the GRC and Security teams immediately via the enterprise security incident reporting process.

Until a dedicated AI Incident Response Playbook is established (see [05-ISO42001-Gap-Assessment — GAP-001](05-ISO42001-Gap-Assessment.md)), AI incidents are managed under the existing Security Incident Response Plan with GRC oversight.

Failure to report a known or suspected AI security incident is a policy violation.

---

## 9. Exceptions

Any deviation from this policy requires:

- Formal written risk acceptance
- Approval from the Security and GRC teams
- Executive sign-off for High or Critical risk exceptions
- Documentation in the AI Risk Register with a defined review date

---

## 10. Policy Review

This policy is reviewed:

- Annually as standard
- After any major AI security incident
- Following material changes to applicable regulations (GDPR, EU AI Act, ISO 42001)
- When a new AI system tier or category is introduced

---

*Last Updated: 2026-06-26* 
