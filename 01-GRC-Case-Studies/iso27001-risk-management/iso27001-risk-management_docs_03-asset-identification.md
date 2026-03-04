# 03 — Asset Identification & Bundling

[← Back to Project Overview](../README.md)

---

## Approach

Asset identification followed a two-stage process:

1. **Granular inventory** — 23 individual information assets identified and scored
2. **Strategic bundling** — Assets consolidated into 8 business-aligned bundles for executive reporting

This approach ensures analytical rigor at the technical level while producing governance-ready outputs for decision-makers.

## Stage 1: Detailed Asset Inventory (23 Assets)

Each asset was scored using the expanded 4-criteria model (Revenue 0.35, Legal 0.30, Reputation 0.20, Continuity 0.15).

| # | Information Asset | C1 | C2 | C3 | C4 | Weighted Total |
|---|---|---|---|---|---|---|
| 1 | AD Service | 4 | 2 | 2 | 4 | 3.00 |
| 2 | AD SQL DB | 4 | 3 | 3 | 5 | 3.65 |
| 3 | DNS Service | 3 | 1 | 1 | 3 | 2.00 |
| 4 | DNS SQL DB | 3 | 1 | 2 | 4 | 2.35 |
| 5 | TAS-GL (General Ledger) | 5 | 3 | 5 | 5 | 4.40 |
| 6 | TAS-AP (Accounts Payable) | 3 | 2 | 3 | 4 | 2.85 |
| 7 | TAS-Pay (Payroll) | 3 | 5 | 4 | 4 | 4.00 |
| 8 | TERP-Web DB (E-commerce) | 5 | 5 | 5 | 3 | 4.70 |
| 9 | Opt-HR Medical Records | 1 | 5 | 5 | 3 | 3.30 |
| 10 | TAS-Bank Data | 5 | 5 | 5 | 4 | 4.85 |
| 11 | TAS-AR (Accounts Receivable) | 4 | 1 | 3 | 4 | 2.90 |
| 12 | TERP-CRM | 3 | 2 | 4 | 3 | 2.90 |
| 13 | TDA-Inventory | 4 | 1 | 2 | 3 | 2.55 |
| 14 | Opt-Time Records | 2 | 3 | 2 | 3 | 2.45 |
| 15 | TDA-PO History | 2 | 1 | 1 | 2 | 1.50 |
| 16 | TDA-SO History | 2 | 1 | 1 | 3 | 1.65 |
| 17 | Email / Exchange DB | 2 | 1 | 2 | 3 | 1.85 |
| 18 | TDA-Warehouse Logic | 2 | 1 | 1 | 4 | 1.65 |
| 19 | TAS-Fixed Assets | 1 | 1 | 1 | 2 | 1.15 |
| 20 | HR Performance Reviews | 1 | 4 | 4 | 2 | 2.65 |
| 21 | Marketing / Strategic Plans | 1 | 1 | 5 | 4 | 2.25 |
| 22 | BARS Backup Data Sets | 1 | 1 | 2 | 5 | 1.80 |
| 23 | Network Configuration Files | 1 | 1 | 1 | 4 | 1.45 |

## Stage 2: Executive Asset Bundles

Following quantitative scoring, assets were grouped into **8 strategic bundles** to:

- Improve executive readability
- Align risk reporting to business capabilities
- Reduce reporting complexity
- Support governance-level decision-making

### Bundle Rankings

| Asset Bundle | Owner | Classification | Data Types | Weighted Score |
|---|---|---|---|---|
| **TERP-Web** (E-commerce) | Sales / IT | Restricted | PCI, Customer Data | **4.80** |
| **TAS-Bank Data** | CFO | Highly Confidential | Bank Credentials | **4.70** |
| **TAS-GL** (General Ledger) | CFO | Confidential | Financial Records | **4.45** |
| **TAS-Pay** (Payroll/PII) | HR | Restricted | PII, Medical Data | **3.80** |
| **AD SQL DB** (Identity) | IT Manager | Highly Confidential | Credentials | **3.40** |
| **Fleet Logistics** | Distribution | Confidential | GPS, Logs | **2.85** |
| **Client CRM** | Sales | Confidential | Sales Data | **2.55** |
| **Enterprise Backups** | IT | Confidential | All Systems Data | **1.80** |

### Visual: Weighted Asset Ranking

![Asset Ranking Chart](../assets/asset-ranking-chart.png)

### Key Observations

- **TERP-Web and TAS-Bank** dominate the ranking — both carry direct revenue impact AND high regulatory exposure (PCI, financial data)
- **TAS-Pay** ranks 4th despite lower revenue impact due to significant legal/regulatory liability (PII, medical records)
- **Enterprise Backups** rank lowest individually but represent a **systemic risk multiplier** — if compromised, all other assets are affected
- **AD SQL DB** is a critical infrastructure dependency — a single point of failure for enterprise identity management

### Bundling Rationale

The bundling methodology reflects standard enterprise risk aggregation practices:

- Assets sharing the same **business function** are grouped (e.g., all accounting modules under TAS-GL)
- Assets sharing the same **risk owner** are aligned for governance accountability
- The **classification level** of a bundle is set by its highest-sensitivity component

---

*Previous: [← Risk Assessment Methodology](./02-risk-assessment-methodology.md) | Next: [Threat Analysis →](./04-threat-analysis.md)*
