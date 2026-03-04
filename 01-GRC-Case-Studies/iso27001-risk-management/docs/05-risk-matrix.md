# 05 — Risk Matrix

[← Back to Project Overview](../README.md)

---

## Risk Heat Map

The risk matrix plots the **top 5 asset bundles** against the **5 threat categories** using Likelihood × Impact scoring (1–25 scale).

![Risk Matrix Heatmap](../assets/risk-matrix-heatmap.png)

### Risk Rating Scale

| Score | Rating | Color |
|-------|--------|-------|
| 21–25 | 🔴 Critical | Red |
| 16–20 | 🟠 High | Orange |
| 11–15 | 🟡 Medium | Yellow |
| 6–10 | 🟢 Low | Green |
| 1–5 | 🔵 Very Low | Blue |

## Full Risk Matrix (Numerical)

| Asset | Info Extortion | Software Attacks | Human Error | Obsolescence | HW Failure |
|---|---|---|---|---|---|
| **TAS-Bank** | 🟠 20 | 🟡 15 | 🔴 **25** | 🟡 15 | 🟢 8 |
| **TERP-Web** | 🟠 20 | 🔴 **25** | 🔴 **25** | 🔴 **25** | 🟢 8 |
| **TAS-GL** | 🔴 **25** | 🟢 8 | 🟠 16 | 🟠 16 | 🟡 15 |
| **TAS-Pay** | 🟠 16 | 🟠 20 | 🟠 20 | 🟡 12 | 🟢 9 |
| **AD SQL DB** | 🔴 **25** | 🟢 9 | 🟡 12 | 🔴 **25** | 🟡 15 |

## Critical Red-Zone Analysis (Score = 25)

Six intersections reached the maximum critical score, requiring **immediate mitigation**:

| # | Asset × Threat | Why It's Critical |
|---|---|---|
| 1 | **Human Error × TAS-Bank** | Phishing attack leading to bank credential compromise — direct financial loss |
| 2 | **Software Attacks × TERP-Web** | SQL injection on internet-facing e-commerce platform — PCI breach, revenue disruption |
| 3 | **Human Error × TERP-Web** | Employee misconfiguration or social engineering exposing customer payment data |
| 4 | **Obsolescence × TERP-Web** | Unpatched e-commerce platform with known vulnerabilities — predictable exploitation |
| 5 | **Info Extortion × TAS-GL** | Ransomware encrypting general ledger — complete financial operations shutdown |
| 6 | **Obsolescence × AD SQL DB** | End-of-life identity infrastructure — single point of failure for all authentication |

## Risk Concentration Patterns

### By Asset (Most Exposed)
- **TERP-Web** has **3 critical scores** and **1 high score** — the most exposed asset in the enterprise
- **AD SQL DB** has **2 critical scores** — infrastructure dependency risk

### By Threat (Most Damaging)
- **Human Error** produces **2 critical scores** — the most consistently dangerous threat vector
- **Obsolescence** produces **2 critical scores** — a predictable, preventable risk

### Strategic Insight
The risk concentration reveals a **dual vulnerability pattern**:
1. **Revenue-facing systems** (TERP-Web, TAS-Bank, TAS-GL) are exposed to human and software threats
2. **Infrastructure systems** (AD SQL DB) are exposed to obsolescence and extortion

This pattern requires a **two-track mitigation strategy**: people-focused controls (training, awareness) AND technology-focused controls (patching, replacement, hardening).

---

*Previous: [← Threat Analysis](./04-threat-analysis.md) | Next: [Risk Treatment Plan →](./06-risk-treatment-plan.md)*
