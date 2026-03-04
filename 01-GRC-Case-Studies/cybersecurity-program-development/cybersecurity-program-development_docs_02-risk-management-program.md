# 02 — Cybersecurity Risk Management Program

[← Back to Project Overview](../README.md)

---

## Program Objective

Establish a structured, repeatable risk management program that identifies, evaluates, treats, and monitors cybersecurity risks across CGT's operations — transitioning from an informal, reactive posture to a governance-driven, risk-informed approach.

## Program Structure

The risk management program is organized into **3 phases** with a continuous improvement loop:

```
Phase 1: Governance & Framework Design
    ↓
Phase 2: Risk Assessment & Treatment
    ↓
Phase 3: Monitoring & Continuous Improvement
    ↺ (feeds back into Phase 1)
```

## Program Components

| Component | Description |
|---|---|
| **Governance Structure** | Risk ownership, reporting lines, executive oversight |
| **Risk Management Framework** | Methodology for identifying, assessing, and treating risks |
| **Policies, Standards, and Procedures** | Documented rules governing risk-related activities |
| **Roles and Responsibilities** | Clear accountability for risk decisions at every level |

---

## Phase 1: Governance & Framework Design

### Objectives
- Establish risk appetite and tolerance levels aligned with CGT's business goals
- Define risk management roles (Board, CEO, COO, CISO, CIO)
- Develop risk management policies

### Key Activities

| Activity | Description |
|---|---|
| **Define Risk Appetite** | CGT's tolerance for risk to intellectual property vs. operational systems vs. corporate data |
| **Establish Risk Governance** | CISO leads risk management; reports to COO; quarterly briefings to CEO |
| **Develop Risk Management Policy** | Formal document mandating risk assessment, treatment, and review cycles |
| **Create Governance Charter** | Defines authority, scope, and accountability for the risk management program |

### Key Deliverables
- ✅ Risk Management Policy Document
- ✅ Governance Charter and Organizational Structure

### CGT-Specific Considerations
- **Risk appetite for IP assets (source code) should be very low** — any compromise directly threatens CGT's competitive position and revenue
- **Risk appetite for corporate systems (HR, Accounting) can be moderate** — important but not existential
- **Risk appetite for testing environments (Racks 6–15) can be higher** — these are designed for external access and are inherently more exposed

---

## Phase 2: Risk Assessment & Treatment

### Phase 2a: Risk Assessment

#### Asset Identification

CGT's critical assets, prioritized by business impact:

| Priority | Asset Category | Examples | Risk Driver |
|---|---|---|---|
| **Tier 0** | Game Source Code & Development Platforms | Rack 2 servers (DevelopIT) | Core IP — existential risk if compromised |
| **Tier 0** | Backup Infrastructure | Rack 3 (SAN), Cloud backups | Recovery capability for all other assets |
| **Tier 1** | Client & Financial Data | Clientz, Account-Master, HRIS/Payroll | Regulatory exposure (GDPR, financial) |
| **Tier 1** | Production Infrastructure | Rack 1 servers, firewalls, VPN | Operational continuity |
| **Tier 2** | Testing Environments | Racks 6–15 (VM-based cloud testing) | Controlled exposure by design |
| **Tier 2** | Marketing & Sales Tools | MarketIT, SellIT, Webz | Supporting functions |

#### Threat and Vulnerability Identification

| Threat Category | CGT-Specific Scenarios | Current Vulnerability |
|---|---|---|
| **Insider Threat** | Developer exfiltrating source code; disgruntled employee sabotage | High — no DLP, no data classification, no monitoring |
| **Ransomware / Extortion** | Encryption of Rack 2 (source code) or Rack 1 (corporate systems) | Medium — backups exist but no IR plan |
| **Software Supply Chain** | Compromised development tools or third-party libraries | High — no secure SDLC, no code review |
| **Social Engineering** | Phishing targeting employees with system access | High — no awareness training |
| **External Attack** | Exploitation of testing environments (Racks 6–15) exposed to external testers | Medium — firewall exists but no vulnerability scanning |
| **Physical Breach** | Unauthorized access to data center (Room 127 equivalent) | Low — strong physical security (Ironclad) |

#### Risk Analysis and Evaluation
- Evaluate likelihood and impact of each risk against CGT's operations
- Prioritize risks based on CGT's defined risk appetite (Phase 1)
- Document in formal risk register with risk owners

#### Key Deliverables
- ✅ Asset Register (categorized by tier)
- ✅ Risk Register with Prioritized Risks

### Phase 2b: Risk Treatment Strategies

Five treatment options, applied based on risk level and business context:

| Strategy | Definition | CGT Application |
|---|---|---|
| **Defense (Avoidance)** | Implement controls to prevent the risk | Firewall hardening, SIEM deployment, access controls for Rack 2 |
| **Transference** | Shift risk to a third party | Cyber insurance; SLA with Ironclad Security; cloud backup provider SLA |
| **Mitigation** | Reduce likelihood or impact | Incident response plan, disaster recovery procedures, security awareness training |
| **Acceptance** | Consciously accept residual risk | Low-value assets (marketing materials, public website content) |
| **Termination** | Eliminate the risk source | Decommission non-critical or legacy systems; restrict testing environment scope |

#### CGT-Tailored Recommendations

| Recommendation | Target Risk | Treatment Type |
|---|---|---|
| Enhance firewall rules and deploy endpoint security for Rack 2 | Source code theft | Defense |
| Formalize cybersecurity policies and incident response plan | All risks | Mitigation |
| Strengthen SLA with Ironclad Security to include cyber-physical scenarios | Physical breach | Transference |
| Deploy SIEM using ManageIT integration | Undetected threats | Defense |
| Implement secure SDLC practices for development teams | Supply chain / code vulnerabilities | Defense |

#### Key Deliverables
- ✅ Risk Treatment Plan Document
- ✅ Implementation Roadmap for Controls and Policies

---

## Phase 3: Monitoring & Continuous Improvement

### Continuous Monitoring

| Activity | Tool / Method | Frequency |
|---|---|---|
| Network and server monitoring | ManageIT (existing) + SIEM (new) | Continuous |
| Vulnerability scanning | New tooling (e.g., Nessus, OpenVAS) | Monthly |
| Access review | Manual review of privileged accounts | Quarterly |
| Policy compliance audit | Internal audit against policy portfolio | Annually |

### Incident Response and Review
- Establish Incident Response Team (from cybersecurity unit)
- Define escalation procedures and communication protocols
- Conduct post-incident analysis and update risk register

### Training and Awareness
- Ongoing employee cybersecurity training (all staff)
- Phishing simulations (quarterly)
- Reinforce and formalize existing no-BYOD and physical security policies

### Key Deliverables
- ✅ Monitoring Reports
- ✅ Updated Risk and Treatment Registers
- ✅ Training Records and Completion Tracking

---

## Summary: Program Lifecycle

| Phase | Focus | Key Deliverables |
|---|---|---|
| **Phase 1** | Governance & Framework | Risk Management Policy, Governance Charter |
| **Phase 2a** | Risk Assessment | Asset Register, Risk Register |
| **Phase 2b** | Risk Treatment | Treatment Plan, Implementation Roadmap |
| **Phase 3** | Monitoring & Improvement | Monitoring Reports, Updated Registers, Training Records |

The program operates as a **continuous cycle** — Phase 3 findings feed back into Phase 1 governance reviews, ensuring the program evolves with CGT's threat landscape and business growth.

---

*Previous: [← Cybersecurity Team Structure](./01-cybersecurity-team-structure.md) | Next: [Policy Framework →](./03-policy-framework.md)*
