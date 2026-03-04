# 02 — Risk Assessment Methodology

[← Back to Project Overview](../README.md)

---

## Approach Overview

The risk assessment follows a structured lifecycle aligned with ISO/IEC 27005 principles:

```
Asset Identification → Classification & Ownership → Threat Identification
    → Weighted Prioritization → Likelihood × Impact Scoring → Risk Treatment
```

This methodology combines **quantitative scoring** with **business-aligned bundling** to produce actionable, defensible risk assessments suitable for both technical and executive audiences.

## Risk Scoring Model

### Risk Score Formula

```
Risk Score = Likelihood × Impact
```

Both Likelihood and Impact are scored on a **1–5 scale**, producing a risk score range of **1–25**.

### Risk Rating Thresholds

| Score Range | Rating | Action Required |
|-------------|--------|----------------|
| 21–25 | 🔴 **Critical** | Immediate mitigation required |
| 16–20 | 🟠 **High** | Mitigation planned within current quarter |
| 11–15 | 🟡 **Medium** | Mitigation planned within 6 months |
| 6–10 | 🟢 **Low** | Accept or monitor |
| 1–5 | 🔵 **Very Low** | Accept |

### Risk Acceptance Criteria

Risks scoring **≥ 20 (High/Critical)** are classified as **unacceptable** and require active treatment through one or more of:
- **Mitigation** — implement controls to reduce likelihood or impact
- **Transfer** — shift risk to a third party (e.g., cyber insurance)
- **Avoidance** — eliminate the activity creating the risk

Risks scoring **< 20** may be **accepted** with documented justification and assigned risk owner approval, subject to quarterly review.

## Asset Scoring Model

A **weighted multi-criteria model** was developed to prioritize information assets based on business impact.

### Executive-Level Criteria (8-Bundle Model)

| Criterion | Weight | Description |
|-----------|--------|-------------|
| C1: Revenue Impact | 0.45 | Direct impact on revenue generation if asset is compromised |
| C2: Legal/Regulatory Liability | 0.35 | Exposure to regulatory penalties, legal action, or compliance violations |
| C3: Cost of Protection | 0.10 | Relative cost and complexity of implementing protective controls |
| C4: Recovery Complexity | 0.10 | Difficulty and time required to restore the asset after an incident |

### Detailed Scoring Criteria (23-Asset Model)

During analysis refinement, the model was expanded to include additional dimensions:

| Criterion | Weight | Description |
|-----------|--------|-------------|
| C1: Revenue Impact | 0.35 | Direct financial impact |
| C2: Legal/Regulatory Exposure | 0.30 | Compliance and legal risk |
| C3: Reputational Impact | 0.20 | Brand and customer trust damage |
| C4: Operational Continuity | 0.15 | Business process disruption |

> **Model Evolution Note:** The initial executive model weighted Revenue (45%) and Legal Exposure (35%) to reflect immediate financial sensitivity. The expanded 23-asset model incorporates Reputational and Continuity dimensions, reflecting a more mature enterprise risk perspective consistent with advisory methodologies where long-term reputational damage and operational resilience are material risk drivers.

## Threat Scoring Model

Threats were evaluated using a separate weighted model:

| Criterion | Weight | Description |
|-----------|--------|-------------|
| C1: Likelihood | 0.35 | Probability of occurrence given BSI's current controls |
| C2: Economic Impact | 0.30 | Financial damage if the threat materializes |
| C3: Current Vulnerability | 0.25 | BSI's current exposure level to this threat |
| C4: Detection Difficulty | 0.10 | How hard it is to detect the threat with current capabilities |

## Methodology Strengths

- **Quantitative and defensible** — weighted scores provide auditable, reproducible results
- **Business-aligned** — criteria reflect business priorities, not just technical severity
- **Scalable** — the same model can be applied as BSI expands its ISMS scope
- **Executive-friendly** — asset bundling translates granular technical data into governance-level insights

---

*Previous: [← Organizational Context](./01-organizational-context.md) | Next: [Asset Identification →](./03-asset-identification.md)*
