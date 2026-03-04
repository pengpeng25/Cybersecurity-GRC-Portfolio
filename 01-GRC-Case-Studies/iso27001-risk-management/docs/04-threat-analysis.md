# 04 — Threat Analysis

[← Back to Project Overview](../README.md)

---

## Approach

Threat analysis followed a two-stage process:

1. **Broad environmental scan** — 12 specific threat scenarios identified across technical, human, environmental, operational, and strategic vectors
2. **Strategic consolidation** — Threats grouped into 5 weighted categories for executive reporting and risk matrix construction

## Stage 1: Comprehensive Threat Inventory

| # | Threat Scenario (BSI-Specific) | Threat Classification |
|---|---|---|
| 1 | Ransomware targeting TAS-GL/Pay financial systems | Information Extortion |
| 2 | Phishing campaigns targeting employees | Human Error / Social Engineering |
| 3 | SQL injection on TERP-Web e-commerce platform | Software Attacks |
| 4 | Server or NAS disk failure | Technical Hardware Failure |
| 5 | Unpatched ERP software vulnerabilities | Technical Software Failure |
| 6 | Competitor stealing client lists | Espionage / Trespass |
| 7 | Flooding in server room (Room 127) | Forces of Nature |
| 8 | Running obsolete Windows Server 2016 systems | Technological Obsolescence |
| 9 | Theft of delivery truck laptops | Theft |
| 10 | ISP outage disrupting operations | Deviation in Quality of Service |
| 11 | Disgruntled technician damaging server racks | Sabotage / Vandalism |
| 12 | Patent infringement of software | Intellectual Property Compromise |

> This inventory demonstrates breadth of environmental scanning across technical, human, environmental, operational, and strategic threat vectors.

## Stage 2: Weighted Threat Categories

The 12 scenarios were consolidated into 5 strategic threat categories and scored using a weighted model:

**Scoring Criteria:**
- C1: Likelihood (0.35)
- C2: Economic Impact (0.30)
- C3: Current Vulnerability (0.25)
- C4: Detection Difficulty (0.10)

| Threat Category | C1 | C2 | C3 | C4 | Weighted Total | Rank |
|---|---|---|---|---|---|---|
| **Information Extortion** (Ransomware) | 5 | 5 | 4 | 3 | **4.55** | 1 |
| **Human Error** (Phishing / Social Engineering) | 5 | 4 | 5 | 2 | **4.40** | 2 |
| **Software Attacks** (Malware, Injection) | 4 | 5 | 4 | 4 | **4.30** | 3 |
| **Technological Obsolescence** | 3 | 4 | 5 | 3 | **3.80** | 4 |
| **Technical Hardware Failure** | 3 | 4 | 4 | 2 | **3.45** | 5 |

## Key Threat Insights

### 🔴 Information Extortion (Ransomware) — Highest Ranked
- BSI has **no incident response plan** and **no endpoint protection strategy**
- Financial systems (TAS-GL, TAS-Bank) are high-value ransomware targets
- Weekly cloud backups provide limited recovery capability (RPO = 7 days)
- **Current vulnerability is high** due to absence of security awareness training

### 🟠 Human Error — Second Highest
- BSI has **no security awareness program** — employees are untrained against phishing
- Scores highest on **Current Vulnerability (5/5)** — the most exploitable vector
- Human error is the entry point for most ransomware and data breach incidents
- Small IT team (2 people) means limited capacity to detect social engineering

### 🟠 Software Attacks — Third Highest
- TERP-Web (e-commerce) is **internet-facing** with PCI data — prime target for SQL injection
- No evidence of web application firewall (WAF) or regular vulnerability scanning
- Highest **Detection Difficulty (4/5)** among all threat categories

### 🟡 Technological Obsolescence
- Servers A and B (Active Directory, DNS) are running **end-of-life hardware**
- Windows Server 2016 is approaching end of extended support
- Scores highest on **Current Vulnerability (5/5)** — known, predictable risk

### 🟢 Technical Hardware Failure
- Mitigated partially by existing NAS cross-replication and cloud backup
- Lowest overall score but still relevant given aging infrastructure

---

*Previous: [← Asset Identification](./03-asset-identification.md) | Next: [Risk Matrix →](./05-risk-matrix.md)*
