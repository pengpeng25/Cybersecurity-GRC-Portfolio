# 01 — Cybersecurity Team Structure

[← Back to Project Overview](../README.md)

---

## Context

CGT has a mature IT division (~15 staff across SysOps, NetOps, and ServOps) but **zero dedicated cybersecurity personnel**. The CIO oversees IT operations, but there is no security governance, no policy ownership, and no incident response capability.

The objective is to design a cybersecurity unit that addresses CGT's immediate gaps while remaining scalable as the program matures.

## Current Strengths to Build On

Before designing the new unit, it's important to recognize what CGT already does well:

| Category | Existing Controls |
|---|---|
| **Technical** | Centralized infrastructure, no local data storage, Check Point firewall, VPN-only access, near real-time SAN backups, encrypted offsite backups |
| **Administrative** | No BYOD policy (informal), VPN restricted to corporate IT |
| **Physical** | 24/7 outsourced security (Ironclad Security), CCTV, photo ID keycards, escorted visitors |

**The gap is not technical — it's organizational and procedural.** CGT needs people, policies, and processes to govern the technology it already has.

## Critical Gaps Requiring Dedicated Staff

| Gap | Risk |
|---|---|
| No cybersecurity leadership | No strategic direction, no risk ownership |
| No formal policies or procedures | No enforceable standards for data handling, access, or incident response |
| No monitoring or SIEM | Threats go undetected |
| No vulnerability scanning or patch management | Known vulnerabilities remain exploitable |
| No secure SDLC practices | Game source code — CGT's most valuable asset — developed without security review |
| No data classification | No differentiation between public marketing data and proprietary source code |
| No security awareness training | Employees are untrained against social engineering |

## Proposed Team Structure: GRC-Based Tiered Model

The cybersecurity unit is organized into three functional tiers:

| Tier | Function | Purpose |
|---|---|---|
| **Define** | Strategy, Policy, Governance, Risk Management | Set direction, ensure accountability |
| **Build** | Architecture, Security Engineering | Design and implement secure infrastructure |
| **Operate** | Monitoring, Incident Response, Daily Operations | Maintain daily protection and response |

This model separates **strategic governance** from **technical implementation** from **operational execution** — preventing the common failure mode where security staff are too busy firefighting to develop policy.

## Organizational Placement: Where Should the CISO Report?

| Reporting Line | Pros | Cons | Recommendation |
|---|---|---|---|
| **CIO** | Strong technical alignment; easy integration | Conflict of interest — CIO prioritizes uptime over security; lacks independence | ❌ Not recommended |
| **CEO** | Maximum independence; board-level visibility | Limited operational involvement; may be too removed from daily operations | Suitable for high-regulation sectors |
| **COO** | Operational alignment with dev/testing; independent from IT | Needs IT coordination mechanisms | ✅ **Recommended for CGT** |

### Why COO?

- CGT's primary risk is **intellectual property** — game source code lives in the Development division under the COO
- The CISO needs **independence from IT** (which manages the infrastructure being secured)
- The COO oversees the **operational workflows** (development, testing, client support) that security must integrate with
- This placement ensures the CISO has **direct access to the teams creating and handling CGT's most valuable assets**

## Recommended Phase 1: Initial 6-Person Team

| Tier | Title | Functional Role | Source | Key Qualifications |
|---|---|---|---|---|
| **Define** | CISO | Leads strategy, policy, governance, risk oversight | New hire | Executive experience; CISSP/CISM; cross-functional leadership |
| **Define** | Cybersecurity Policy & Risk Manager | Builds risk register, policies, supports compliance | New hire or upskill | 5+ years GRC; NIST/ISO framework experience |
| **Build** | Security Architect (shared) | Designs secure infrastructure, network zones, firewall rules | Cross-functional from IT | Networking, firewall/DMZ design, architecture experience |
| **Build** | Security Engineer | Installs/configures SIEM, EDR, MFA tools | New hire or upskill | Patching, scripting, Security+ |
| **Operate** | Security Analyst | Monitors systems, scans for vulnerabilities, triages alerts | New hire or upskill | Log analysis, vulnerability scanning, patch management |
| **Operate** | Security Awareness Coordinator | Delivers SETA program, phishing simulations, training | From HR or Client Support | Training/communication skills, basic infosec knowledge |

### Staffing Rationale

- **6 people is the minimum viable team** — covers governance (Define), implementation (Build), and daily operations (Operate)
- **Cross-functional sourcing** reduces hiring cost — the Security Architect and Awareness Coordinator can be drawn from existing IT and HR/Support staff
- **The CISO and Policy & Risk Manager must be dedicated hires** — these roles require independence and specialized expertise

## Phase 2: Future Expansion Roles

As the program matures, the following roles support SDLC security, automation, and deeper operational defense:

| Tier | Title | Functional Role | Source |
|---|---|---|---|
| **Build** | Application Security Specialist | Security in SDLC, code reviews, security testing | From Development |
| **Build** | Security Automation Engineer | Automates scans, CI/CD pipeline security | From Dev/Test |
| **Operate** | SOC Analyst (Tier 1–2) | Real-time alert monitoring, log triage, escalation | Cross-trained |
| **Operate** | IR & Forensics Analyst | Root cause analysis, incident containment, evidence preservation | New hire |
| **Operate** | Security Administrator | Manages access controls, firewalls, MFA, VPN | From IT |

### Why Application Security Is a Phase 2 Priority

CGT's **core business is software development**. The Development division runs three 5-member teams producing game titles. Yet there is:
- No mention of secure coding practices
- No code review for security vulnerabilities
- No security testing integrated into the SDLC

An Application Security Specialist embedded in the Development workflow would address this critical gap — but requires the foundational governance (Phase 1) to be in place first.

## Updated Organizational Chart (Proposed)

```
CEO — Alan Hake
├── COO — Richard Xavier
│   ├── Gaming Development Division
│   │   ├── Development (3 teams × 5 programmers)
│   │   ├── Testing
│   │   └── Client Support
│   │
│   └── 🔒 Cybersecurity Unit (NEW)
│       ├── CISO
│       ├── Define: Policy & Risk Manager
│       ├── Build: Security Architect (shared w/ IT)
│       ├── Build: Security Engineer
│       ├── Operate: Security Analyst
│       └── Operate: Awareness Coordinator (shared w/ HR)
│
├── CBO — Rachel Xieng
│   ├── Accounting
│   ├── HR
│   └── Marketing
│
└── CIO — Paul Alexander
    ├── SysOps
    ├── NetOps
    └── ServOps
```

---

*Next: [Risk Management Program →](./02-risk-management-program.md)*
