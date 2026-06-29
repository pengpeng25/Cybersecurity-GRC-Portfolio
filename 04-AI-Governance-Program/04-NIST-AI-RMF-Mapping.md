# 04 — NIST AI RMF Mapping

> **SimulFlow S.r.l.** *(Fictional Organization)*
> Source: [01-AI-Inventory](01-AI-InventoryE.md) · [02-AI-Risk-Assessments](02-AI-Risk-Assessments.md) · [03-AI-Risk-Register](03-AI-Risk-Register.md)
> Framework: NIST AI Risk Management Framework (AI RMF 1.0)

---

## Purpose

This document demonstrates how SimulFlow's Enterprise AI Governance Program aligns with the four core functions of the NIST AI RMF. Governance activities are integrated into existing enterprise risk management processes to ensure AI systems are governed throughout their lifecycle.

---

## NIST AI RMF Overview

| Function | Objective |
|----------|-----------|
| **Govern** | Establish governance structures, policies, accountability, and oversight |
| **Map** | Understand AI systems, business context, stakeholders, and risks |
| **Measure** | Assess, analyze, and monitor AI risks |
| **Manage** | Prioritize, treat, monitor, and communicate AI risks |

These functions are iterative and support continuous improvement rather than a sequential implementation process.

> For the full AI risk lifecycle including ownership and escalation criteria, see [03-AI-Risk-Register — Risk Lifecycle](../03-AI-Risk-Register/README.md).

---

## GOVERN

**Objective:** Establish organizational accountability and governance for AI systems.

| Governance Activity | Portfolio Evidence | TryHackMe Basis |
|--------------------|-------------------|-----------------|
| AI Governance Policy | 07-AI-Governance-Policy | Securing AI Systems — governance principles |
| Executive oversight | 08-Executive-Dashboard | — |
| AI Inventory ownership | 01-AI-Inventory | AI Fundamentals — asset classification |
| Risk ownership assignment | 03-AI-Risk-Register | — |
| Governance review cycle | Quarterly AI Governance Review | — |

**Maturity: Level 3 — Defined**

Governance structures and policies are documented with defined ownership. Remaining opportunities:

| Priority | Gap |
|----------|-----|
| High | Formal AI Steering Committee not yet established |
| Medium | AI ethics review process not formalized |
| Medium | Enterprise AI approval workflow in development |

---

## MAP

**Objective:** Understand AI systems, business context, stakeholders, and potential impacts.

| Governance Activity | Portfolio Evidence | TryHackMe Basis |
|--------------------|-------------------|-----------------|
| AI Inventory | 01-AI-Inventory | AI Fundamentals — system classification |
| Business owner identification | 01-AI-Inventory | — |
| Data classification | 01-AI-Inventory | — |
| Threat modelling | 02-AI-Risk-Assessments | AI Threat Modelling + Assessment room |
| AI vendor identification | 06-Vendor-Risk-Assessment | AI Supply Chain Security module |

**Maturity: Level 4 — Managed**

Complete enterprise AI inventory with business ownership, data classification, and third-party AI visibility established. Remaining opportunity:

| Priority | Gap |
|----------|-----|
| Low | Automated AI asset discovery not yet implemented |

---

## MEASURE

**Objective:** Evaluate AI risks through structured assessment and continuous monitoring.

| Governance Activity | Portfolio Evidence | TryHackMe Basis |
|--------------------|-------------------|-----------------|
| AI risk assessments | 02-AI-Risk-Assessments | Securing AI Systems — OWASP LLM Top 10 |
| Risk rating methodology | 02-AI-Risk-Assessments | AI Threat Modelling + Assessment room |
| AI Risk Register | 03-AI-Risk-Register | — |
| Residual risk evaluation | 03-AI-Risk-Register | — |
| AI metrics and reporting | 08-Executive-Dashboard | — |

**Maturity: Level 4 — Managed**

Risk evaluation covers likelihood, impact, inherent and residual risk, treatment tracking, and OWASP LLM Top 10 alignment across all AI systems. Remaining opportunities:

| Priority | Gap |
|----------|-----|
| High | Automated AI security monitoring not yet implemented |
| Medium | Continuous model evaluation not yet established |
| Medium | AI performance and trustworthiness metrics to be defined |

---

## MANAGE

**Objective:** Prioritize and manage AI risks throughout the AI lifecycle.

| Governance Activity | Portfolio Evidence | TryHackMe Basis |
|--------------------|-------------------|-----------------|
| Risk treatment planning | 03-AI-Risk-Register | — |
| Risk acceptance process | Risk Appetite Statement | — |
| Executive reporting | 08-Executive-Dashboard | — |
| Vendor risk management | 06-Vendor-Risk-Assessment | AI Supply Chain Security module |
| Continuous improvement | 09-Control-Improvement-Roadmap | — |

**Maturity: Level 3 — Defined**

Risk ownership, treatment tracking, and quarterly governance reviews are operational. Maturity is constrained by two specific gaps not yet addressed:

| Priority | Gap |
|----------|-----|
| High | AI incident response playbooks not yet developed |
| High | Automated control validation not yet implemented |
| Medium | Continuous AI monitoring pending |

---

## Coverage Assessment

| Function | Maturity | Supporting Deliverables |
|----------|----------|------------------------|
| Govern | Level 3 — Defined | AI Governance Policy, Risk Ownership, Executive Dashboard |
| Map | Level 4 — Managed | AI Inventory, Data Classification, Threat Modelling |
| Measure | Level 4 — Managed | Risk Assessments, Risk Register, Risk Metrics |
| Manage | Level 3 — Defined | Treatment Tracking, Governance Roadmap, Vendor Risk Management |

**Overall AI Governance Maturity: Level 3.5 — Managed and Operational**

The organization has established a functioning AI governance program with documented processes, defined ownership, and operational risk management. Priority improvement areas are AI incident response and automated control validation.

---

## Key Strengths

| Strength | Evidence |
|----------|----------|
| Centralized AI inventory with business ownership | 01-AI-Inventory |
| Structured risk assessment methodology | 02-AI-Risk-Assessments |
| Operational risk register with treatment tracking | 03-AI-Risk-Register |
| OWASP LLM Top 10 alignment across all risk entries | 03-AI-Risk-Register |
| Risk appetite statement governing treatment decisions | 03-AI-Risk-Register |
| Executive-level governance reporting | 08-Executive-Dashboard |

---

## Opportunities for Improvement

| Priority | Recommendation | NIST Function |
|----------|---------------|---------------|
| 🔴 High | Develop AI incident response playbooks | Manage |
| 🔴 High | Implement automated control validation | Manage / Measure |
| 🟡 Medium | Establish cross-functional AI Governance Committee | Govern |
| 🟡 Medium | Automate AI asset discovery and inventory updates | Map |
| 🟡 Medium | Define AI model performance and trustworthiness metrics | Measure |
| 🟢 Low | Conduct annual AI governance maturity assessments | Govern |

---

## Portfolio Linkage

| Document | NIST AI RMF Function |
|----------|---------------------|
| `01-AI-Inventory` | Map |
| `02-AI-Risk-Assessments` | Map · Measure |
| `03-AI-Risk-Register` | Measure · Manage |
| `05-ISO42001-Gap-Assessment` | Govern · Manage |
| `06-Vendor-Risk-Assessment` | Map · Manage |
| `07-AI-Governance-Policy` | Govern |
| `08-Executive-Dashboard` | Govern · Manage |
| `09-Control-Improvement-Roadmap` | Manage |

---

*Last updated: 2026-06-26 · Owner: GRC Team · Next review: 2026-09-26*
