# 03 — Cybersecurity Policy Framework

[← Back to Project Overview](../README.md)

---

## Why Policies Matter at CGT

CGT currently operates with **zero formal cybersecurity policies**. Some practices exist informally (no BYOD, no WiFi, VPN-only access), but none are documented, enforceable, or auditable.

Without formal policies:
- There is no legal basis for disciplinary action against security violations
- There is no standard for employees to follow
- There is no audit trail for compliance
- The CISO has no authority framework to enforce security decisions

## Policy Portfolio Structure

The policy framework follows a **3-tier hierarchy**, each serving a different audience and purpose:

| Tier | Policy Type | Audience | Purpose |
|---|---|---|---|
| **Tier 1** | Enterprise Information Security Policy (EISP) | All employees, executives, board | Strategic direction — the "constitution" of CGT security |
| **Tier 2** | Issue-Specific Security Policies (ISSPs) | Specific departments or user groups | Address specific risk areas (data privacy, acceptable use, etc.) |
| **Tier 3** | System-Specific Security Policies (SysSPs) | Technical staff (IT, NetOps, ServOps) | Technical configuration and operational standards |

```
EISP (Strategic — "What we believe and require")
  ├── ISSP: Player Data Privacy Policy
  ├── ISSP: Acceptable Use Policy
  ├── ISSP: Intellectual Property Protection Policy
  ├── ISSP: Incident Response Policy
  └── ...
      ├── SysSP: Firewall Configuration Policy
      ├── SysSP: Server Hardening Standard
      ├── SysSP: Backup & Recovery Procedures
      └── ...
```

## Core Policy Elements

Every policy in the portfolio must contain:

| Element | Description |
|---|---|
| **Purpose and Scope** | What the policy covers and who it applies to |
| **Roles and Responsibilities** | Who owns, enforces, and complies with the policy |
| **Managerial Guidance** | Policy-level direction for managers |
| **Technical Guidance** | System-specific implementation details (SysSPs) |
| **Enforcement Mechanisms** | Consequences for violations |
| **Review Schedule** | Annual review or upon major organizational changes |

---

## Tier 1: Enterprise Information Security Policy (EISP)

### Purpose
Establishes CGT's strategic commitment to information security, defines the authority of the CISO, and sets the governance framework for all subordinate policies.

### Key Provisions (CGT-Specific)

| Provision | Detail |
|---|---|
| **Security Governance** | CISO reports to COO; cybersecurity unit has authority over security decisions |
| **Data Handling** | All corporate data stored centrally on servers — no local storage on endpoints |
| **Network Access** | LAN-only access via physical connections; no WiFi; VPN restricted to authorized corporate IT |
| **Device Policy** | No BYOD on premises; personal devices stored in lockers/vehicles; use only during authorized breaks |
| **Physical Security** | Outsourced to Ironclad Security; 24/7 monitoring, CCTV, keycard access, escorted visitors |
| **Compliance** | All employees must acknowledge and comply; violations subject to disciplinary action |

### EISP Alignment with CGT Operations
The EISP formalizes practices that already exist informally at CGT (no BYOD, no WiFi, centralized storage) while adding the governance structure (CISO authority, enforcement mechanisms) that is currently missing.

---

## Tier 2: Issue-Specific Security Policies (ISSPs)

### Recommended ISSPs for CGT

| ISSP | Target Risk | Key Provisions |
|---|---|---|
| **Player Data Privacy Policy** | Customer data exposure, GDPR compliance | Gamer data accessed only via Clientz application; no third-party sharing without consent; encrypted backups retained for 2 years |
| **Intellectual Property Protection Policy** | Source code theft, insider threat | Access to Rack 2 (DevelopIT) restricted to authorized developers; no external storage devices; code commits logged and auditable |
| **Acceptable Use Policy** | Misuse of corporate systems | Defines permitted use of corporate systems, email, and internet; prohibits unauthorized software installation |
| **Incident Response Policy** | Uncoordinated response to security events | Defines incident classification, escalation procedures, and communication protocols |
| **Remote Access Policy** | Unauthorized remote connections | VPN access restricted to corporate IT personnel only; MFA required; session logging |
| **Third-Party Access Policy** | External tester risk | External testers access only Racks 6–15 via controlled, isolated environments; no access to corporate network |

### Example: Player Data Privacy Policy

**Scope:** All CGT employees who access, process, or handle customer/gamer data through the Clientz application or any other system.

**Key Rules:**
1. Gamer data shall be accessed **only through the Clientz application** — no direct database queries without CISO authorization
2. Customer data shall **not be shared with third parties** without explicit consent and legal review
3. Customer data backups shall be **encrypted (AES-256)** and retained for a maximum of 2 years
4. Any suspected data breach involving customer data must be reported to the CISO **within 1 hour** of discovery
5. Marketing department access to customer data is limited to **aggregated, anonymized datasets** only

---

## Tier 3: System-Specific Security Policies (SysSPs)

### Recommended SysSPs for CGT

| SysSP | Target System | Key Provisions |
|---|---|---|
| **Firewall Configuration Policy** | Check Point 4800 | Block all unsolicited inbound traffic to Racks 1–3; allow pre-approved IPs to testing servers (Racks 6–15); weekly rule audits |
| **Server Hardening Standard** | All Windows 2016 servers | Baseline configurations, disabled unnecessary services, patch schedule |
| **Backup & Recovery Procedures** | NAS #1/#2, SAN, Cloud backup | Near real-time SAN replication; daily NAS cross-backup; weekly encrypted cloud backup; quarterly restore testing |
| **Database Encryption Standard** | All SQL databases | AES-256 encryption at rest; TLS for data in transit; key rotation schedule |
| **VPN Configuration Policy** | Corporate VPN | Authorized IT personnel only; MFA required; session timeout after 30 minutes of inactivity |

### Example: Firewall Configuration Policy

**Scope:** Check Point 4800 firewall managed by NetOps.

**Key Rules:**
1. **Default deny** — all inbound traffic blocked unless explicitly permitted
2. **Rack 2 (source code servers)** — no inbound connections from external networks under any circumstances
3. **Racks 6–15 (testing environments)** — inbound connections permitted only from pre-approved external tester IPs, logged and reviewed weekly
4. **Outbound traffic** — permitted for business applications; social media and streaming blocked during business hours
5. **Rule audit** — NetOps conducts weekly firewall rule review; CISO reviews quarterly
6. **Change management** — any firewall rule change requires written approval from CISO or Security Architect

---

## Implementation Roadmap

| Phase | Activity | Owner | Timeline |
|---|---|---|---|
| 1 | Conduct policy gap analysis against current informal practices | CISO + Policy & Risk Manager | Month 1 |
| 2 | Draft and approve EISP | CISO → COO → CEO | Month 2 |
| 3 | Draft priority ISSPs (IP Protection, Incident Response, Acceptable Use) | Policy & Risk Manager | Months 2–3 |
| 4 | Draft priority SysSPs (Firewall, Server Hardening, Backup) | Security Architect + IT | Months 3–4 |
| 5 | Company-wide training and policy acknowledgement | Awareness Coordinator | Month 4 |
| 6 | Use ManageIT for policy distribution and tracking | IT Division | Month 4 |
| 7 | Annual policy review cycle established | CISO | Month 12 |

---

*Previous: [← Risk Management Program](./02-risk-management-program.md) | Next: [Contingency Planning →](./04-contingency-planning.md)*
