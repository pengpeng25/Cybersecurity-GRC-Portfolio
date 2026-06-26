# 08 — Executive Dashboard: AI Governance Metrics

> **SimulFlow S.r.l.** *(Fictional Organization)*
> Source: [03-AI-Risk-Register](../03-AI-Risk-Register/README.md) · [06-Vendor-Risk-Assessment](../06-Vendor-Risk-Assessment/README.md) · [05-ISO42001-Gap-Assessment](../05-ISO42001-Gap-Assessment/README.md)
> Frameworks: NIST AI RMF · ISO/IEC 42001
> Reporting Period: Q3 2026

---

## Purpose

This dashboard provides executive-level visibility into the current AI risk posture, governance maturity, and compliance status of AI systems within SimulFlow.

It supports decision-making for:

- Risk acceptance and escalation
- Investment prioritization
- Governance maturity tracking
- Regulatory readiness

---

## 1. AI Risk Overview

### Risk Distribution

| Risk Level | Inherent | Residual |
|------------|:--------:|:--------:|
| 🔴 Critical (17–25) | 3 | 0 |
| 🔴 High (10–16) | 8 | 1 |
| 🟡 Medium (5–9) | 1 | 9 |
| 🟢 Low (1–4) | 0 | 1 |
| **Total** | **11** | **11** |

> Residual risk profile reflects current state after existing controls. One High residual risk (RISK-001 — Prompt Injection) remains open pending completion of adversarial testing program.

### Risk Trend (Quarterly — Inherent Risk)

| Quarter | 🔴 Critical | 🔴 High | 🟡 Medium | Total |
|---------|:-----------:|:-------:|:---------:|-------|
| Q1 2026 | 5 | 6 | 1 | 12 |
| Q2 2026 | 4 | 7 | 1 | 12 |
| Q3 2026 | 3 | 8 | 1 | 11 |

> Critical risks have decreased 40% since Q1 2026, reflecting active remediation and the maturation of the AI governance program. The increase in High-rated risks reflects improved risk identification coverage, including three new risks added in Q3 (RISK-009, RISK-010, RISK-011).

---

## 2. Treatment Progress

### Treatment Status

| Status | Count | Risk IDs |
|--------|:-----:|----------|
| In Progress | 4 | RISK-001, RISK-003, RISK-005, RISK-008 |
| Planned | 7 | RISK-002, RISK-004, RISK-006, RISK-007, RISK-009, RISK-010, RISK-011 |
| Accepted | 1 | RISK-008 |
| Completed | 0 | — |

> All 11 risks have assigned owners and treatment plans. No risks are unmanaged. RISK-008 has been formally accepted per the Risk Appetite Statement — residual risk is Low (4).

### Treatment by Option

| Treatment | Count |
|-----------|:-----:|
| Mitigate | 10 |
| Accept | 1 |
| Transfer | 0 |
| Avoid | 0 |

---

## 3. AI System Risk Heatmap

| AI System | Type | Inherent Risk | Residual Risk | Treatment Status |
|-----------|------|:-------------:|:-------------:|-----------------|
| AI-001 SimulFlow Assistant | Generative LLM | 🔴 Critical | 🔴 High | In Progress |
| AI-002 Knowledge Hub | RAG System | 🔴 High | 🟡 Medium | In Progress |
| AI-003 Workflow Copilot | AI Agent | 🔴 Critical | 🟡 Medium | In Progress |
| AI-004 Coding Assistant | Code LLM | 🔴 High | 🟡 Medium | Planned |
| AI-005 Translation API | Third-Party API | 🔴 High | 🟡 Medium | Planned |
| AI-006 Meeting Assistant | Productivity AI | 🟡 Medium | 🟢 Low | Accepted |

> AI-001 and AI-003 carry the highest inherent risk profiles. AI-001 retains a High residual risk and requires priority executive attention for adversarial testing investment. AI-006 residual risk has been reduced to Low and formally accepted.

---

## 4. OWASP LLM Top 10 Coverage

| OWASP ID | Risk Category | Coverage | Risk IDs |
|----------|--------------|:--------:|----------|
| LLM01 | Prompt Injection | ✅ Covered | RISK-001 |
| LLM02 | Sensitive Information Disclosure | ✅ Covered | RISK-002, RISK-004, RISK-008 |
| LLM03 | Supply Chain | ✅ Covered | RISK-006, RISK-007 |
| LLM04 | Data and Model Poisoning | ✅ Covered | RISK-003 |
| LLM05 | Improper Output Handling | ➖ Not in Register | Identified as future risk |
| LLM06 | Excessive Agency | ✅ Covered | RISK-005 |
| LLM07 | System Prompt Leakage | ✅ Covered | RISK-009 |
| LLM08 | Vector and Embedding Weaknesses | ✅ Covered | RISK-010 |
| LLM09 | Misinformation | ➖ Not in Register | Identified as future risk |
| LLM10 | Unbounded Consumption | ✅ Covered | RISK-011 |

> 8 of 10 OWASP LLM Top 10 categories are covered in the current Risk Register. LLM05 and LLM09 have been identified as potential future risks and will be evaluated in the next quarterly review.

---

## 5. Vendor Risk Overview

| Metric | Value |
|--------|:-----:|
| Total Vendors Assessed | 4 |
| High Criticality Vendors | 2 |
| Approved | 2 |
| Approved with Conditions | 1 |
| Approved with Monitoring | 1 |
| Rejected | 0 |
| Open Conditions Pending | 2 |
| Annual Reviews Scheduled | 4 |

> Azure AI Search has two open conditions requiring resolution within 60 days (penetration testing evidence and EU data boundary confirmation). DeepL API is under active monitoring for GDPR subprocessor changes. No vendors are currently in a non-compliant status.

---

## 6. ISO/IEC 42001 Readiness

| Domain | Maturity | Notes |
|--------|:--------:|-------|
| AI Governance Structure | 85% | Policy and ownership established; Steering Committee pending |
| Risk Management | 90% | Full risk lifecycle operational; automation pending |
| Data Governance | 85% | Classification complete; lifecycle checkpoints in development |
| Supply Chain | 70% | Onboarding process established; continuous monitoring pending |
| AI Monitoring | 60% | Metrics defined; automated monitoring not yet implemented |
| AI Incident Response | 40% | No dedicated playbook; managed under existing SIRP |
| Continuous Improvement | 75% | Roadmap documented; operationalization in progress |
| **Overall Readiness** | **80%** | Aligned with 05-ISO42001-Gap-Assessment |

> Incident response and continuous monitoring are the two domains with the lowest maturity scores and represent the highest-priority investment areas for Q3–Q4 2026.

---

## 7. Key Risk Indicators (KRIs)

| KRI | Threshold | Current Status | Trend |
|-----|-----------|:--------------:|-------|
| Prompt injection attempts detected | < 5 / week | 3 / week | 🟢 Within threshold |
| Unauthorized data access events | 0 | 0 | 🟢 Within threshold |
| Vendor review overdue | 0 | 0 | 🟢 Within threshold |
| Critical risk open > 30 days | 0 | 0 | 🟢 Within threshold |
| High risk open > 90 days | 0 | 0 | 🟢 Within threshold |
| Risks without assigned owner | 0 | 0 | 🟢 Within threshold |
| Open vendor conditions > 60 days | 0 | 0 — due 2026-08-25 | ⚠️ Monitor |

> All KRIs are currently within threshold. The open vendor condition for Azure AI Search approaches its 60-day deadline on 2026-08-25 and should be tracked for the next reporting cycle.

---

## 8. Priority Actions for Executive Decision

The following items require executive-level approval or resource commitment:

| Priority | Action | Owner | Decision Required |
|----------|--------|-------|------------------|
| 🔴 High | Approve budget and scope for AI Incident Response Playbook development | CISO | Q3 2026 |
| 🔴 High | Approve investment in automated AI monitoring tooling | CISO + CTO | Q3 2026 |
| 🟡 Medium | Establish cross-functional AI Governance Committee with executive sponsorship | CEO / CISO | Q4 2026 |
| 🟡 Medium | Confirm Azure AI Search open conditions resolved within SLA | Vendor Risk Manager | 2026-08-25 |
| 🟡 Medium | Approve AI lifecycle governance checkpoint framework | GRC + Product | Q4 2026 |

---

## 9. Executive Summary

The AI governance program demonstrates a controlled and improving risk posture entering Q3 2026.

**Strengths:**
- Critical risks decreased 40% since Q1 2026 through active remediation
- All 11 registered risks have assigned owners and documented treatment plans
- Vendor governance is stable with no non-compliant vendors
- 8 of 10 OWASP LLM Top 10 categories are covered in the Risk Register
- ISO/IEC 42001 overall readiness is at 80%

**Priority Concerns:**
- RISK-001 (Prompt Injection — SimulFlow Assistant) retains a High residual risk and requires additional investment in adversarial testing
- AI incident response capability is the most significant governance maturity gap (40% readiness)
- Automated AI monitoring has not yet been implemented, limiting real-time threat visibility
- Two open vendor conditions require resolution before end of Q3

**Recommendation:** Approve Q3 investment priorities for AI incident response playbook and automated monitoring to advance ISO/IEC 42001 readiness from 80% to an estimated 95%.

---

*Last updated: 2026-06-26*
