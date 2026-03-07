# IT General Controls (ITGC) — Framework & Assessment Guide

> A structured reference for understanding, evaluating, and testing IT General Controls in audit and advisory engagements. Designed to support IT audit activities aligned with COBIT, ISO 27001, and SOX compliance requirements.

---

## 1. What Are IT General Controls?

IT General Controls are the foundational policies, procedures, and technical configurations that ensure the **integrity, confidentiality, and availability** of information systems and the data they process. Unlike application-specific controls, ITGCs operate across the entire IT environment and underpin the reliability of all automated and IT-dependent manual controls.

ITGCs are critical in:

- **Financial audit** (SOX, ISAE 3402) — ensuring automated financial reporting controls operate in a reliable IT environment
- **Compliance audit** (GDPR, NIS2, DORA) — verifying that data protection and operational resilience controls are technically enforced
- **Operational audit** — assessing whether IT processes support business continuity and operational efficiency

### Why ITGCs Matter in GRC Advisory

For organizations like BSI (regional retail, no formal security staff) or CGT (gaming/software, mature IT but no cybersecurity governance), ITGCs represent the **first layer of control maturity** that must be established before higher-level governance frameworks (ISO 27001, NIST CSF) can function effectively.

> **Advisory insight:** When a client has no formal Information Security Policy — as in both the BSI and CGT case studies — ITGC assessment is the natural starting point for any engagement. It provides immediate, actionable findings while building the foundation for broader ISMS implementation.

---

## 2. The Four ITGC Domains

### 2.1 Access Controls

**Objective:** Ensure that only authorized individuals can access systems, applications, and data — and that access is appropriate to their role.

| Control Area | Description | Testing Approach |
|---|---|---|
| User provisioning | New accounts created with documented approval | Sample new hires → verify approval documentation and role assignment |
| Access modification | Role changes trigger access review | Sample role changes → verify access was updated within policy timeframe |
| Termination procedures | Access revoked promptly upon departure | Sample leavers → verify account deactivation date vs. last working day |
| Privileged access | Admin/root accounts restricted and monitored | Obtain privileged user list → verify business justification for each |
| Password policy | Complexity, rotation, and lockout enforced | Review system configuration → verify alignment with policy |
| Segregation of Duties (SoD) | Conflicting roles separated | Map role matrix → identify SoD conflicts (e.g., AP entry + payment approval) |

**Relevance to BSI case study:**
[See case study: ISO27001 Risk-Management Project](../01-GRC-Case-Studies/iso27001-risk-management/README.md)

BSI's Active Directory (Server A) runs on Windows 2016 — an end-of-life platform. Access controls built on unsupported infrastructure are inherently unreliable. The risk assessment identified AD SQL DB as a critical asset (weighted score: 3.65) precisely because it controls authentication for the entire organization. An ITGC assessment would flag:
- No documented access provisioning/deprovisioning process
- Privileged access to Server A not formally restricted
- No evidence of periodic access reviews

!(itgc-matrix-bsi.png)

**Relevance to CGT case study:**
[See case study: Cybersecurity Program Development](../01-GRC-Case-Studies/cybersecurity-program-development/README.md)

CGT enforces strong physical access controls (keycards, CCTV, escorted visitors) and restricts network access (no BYOD, no WiFi, VPN-only for IT). However, there is no formal access management policy for logical access to application servers (Racks 1-2). The proposed Cybersecurity Policy & Risk Manager role would own the design of these controls.

---

### 2.2 Change Management

**Objective:** Ensure that changes to IT systems (applications, infrastructure, configurations) are authorized, tested, and documented before implementation.

| Control Area | Description | Testing Approach |
|---|---|---|
| Change request process | All changes initiated through formal request | Sample changes → verify documented request and business justification |
| Authorization | Changes approved by appropriate authority before implementation | Sample changes → verify approval signatures/timestamps |
| Testing & validation | Changes tested in non-production environment | Sample changes → verify test evidence and sign-off |
| Segregation of environments | Development, testing, and production separated | Review environment architecture → verify logical/physical separation |
| Emergency changes | Expedited process with retrospective approval | Sample emergency changes → verify post-implementation review |
| Rollback procedures | Documented fallback plan for failed changes | Sample changes → verify rollback plan exists |

**Relevance to BSI case study:**
BSI's 12-month remediation roadmap includes server replacement (Q2), backup modernization (Q3), and incident response plan (Q4). Each of these represents a significant IT change that, without formal change management, could introduce new vulnerabilities. The risk assessment identified Technical Hardware Failure (weighted: 3.45) and Technological Obsolescence (weighted: 3.80) as key threats — both directly linked to uncontrolled infrastructure changes.

**Relevance to CGT case study:**
CGT's Development division operates a formal SDLC with dedicated development, testing, and client support teams. However, there is no documented change management process for infrastructure changes managed by SysOps, NetOps, and ServOps. The gap analysis identified "no mention of secure coding practices, code review, or security testing in the SDLC" — a change management control deficiency.

---

### 2.3 IT Operations

**Objective:** Ensure that IT systems are operated reliably, with appropriate monitoring, incident management, and backup/recovery procedures.

| Control Area | Description | Testing Approach |
|---|---|---|
| Job scheduling | Automated processes (backups, batch jobs) run as intended | Review job schedules → verify completion logs and exception handling |
| Backup & recovery | Data backed up regularly and recovery tested | Review backup logs → verify frequency, completeness, and test results |
| Incident management | IT incidents logged, categorized, and resolved | Sample incidents → verify logging, escalation, and resolution |
| Monitoring & alerting | Systems monitored for performance and security events | Review monitoring configuration → verify coverage and alert thresholds |
| Capacity management | System resources adequate for current and projected demand | Review capacity reports → verify trending and planning |
| Physical & environmental | Data center protected from physical threats | Inspect facilities → verify climate control, fire suppression, access |

**Relevance to BSI case study:**
BSI has a structured backup regime (daily NAS replication + weekly cloud backup), but the risk assessment revealed that backup systems (BARS) lack encryption and the NAS infrastructure has not been tested for recovery. Enterprise Backups scored lowest in asset ranking (1.80) not because they're unimportant, but because their current implementation provides limited assurance. An ITGC assessment of IT operations would test:
- Backup completion rates and exception handling
- Recovery Time Objective (RTO) validation through actual restore tests
- Monitoring coverage (BSI has no SIEM or centralized logging)

**Relevance to CGT case study:**
CGT uses ManageIT for network and system monitoring, but there is no formal incident management process. The contingency planning program (IRP/DRP/BCP) designed in the case study addresses this gap, with the Business Impact Analysis identifying Rack 2 (game source code) and Rack 3 (SAN backups) as Tier 0 assets with a 4-hour RTO.

---

### 2.4 System Development Life Cycle (SDLC)

**Objective:** Ensure that new systems and significant modifications are developed, tested, and deployed with appropriate controls embedded from design through implementation.

| Control Area | Description | Testing Approach |
|---|---|---|
| Requirements definition | Business and security requirements documented | Review requirements docs → verify security requirements included |
| Design review | Security architecture reviewed before development | Review design documents → verify security sign-off |
| Testing | Functional, integration, and security testing performed | Review test plans and results → verify coverage and defect resolution |
| User acceptance | Business users validate system meets requirements | Review UAT evidence → verify sign-off before go-live |
| Deployment | Migration to production controlled and documented | Review deployment records → verify authorization and rollback plan |
| Post-implementation review | System performance validated after go-live | Review PIR documentation → verify issues identified and resolved |

**Relevance to CGT case study:**
CGT's core business *is* software development, making SDLC controls both an IT governance concern and a business-critical process. The gap analysis identified that while CGT has dedicated Development and Testing teams with formal workflows, there is no mention of:
- Security requirements in the development process
- Code review or static analysis
- Security testing before release
- Separation of duties between developers and testers deploying to production

The proposed Application Security Specialist role (future hire) would embed security into the SDLC, while the Security Engineer would ensure deployment controls are enforced.

---

## 3. ITGC Testing in Practice

### 3.1 Audit Approach

An ITGC assessment typically follows this lifecycle:

```
Scoping → Walkthrough → Control Identification → Testing → Deficiency Evaluation → Reporting
```

| Phase | Activity | Output |
|---|---|---|
| **Scoping** | Identify in-scope systems, applications, and infrastructure | Scope document with system inventory |
| **Walkthrough** | Interview process owners, observe controls in operation | Walkthrough narratives and flowcharts |
| **Control identification** | Map controls to ITGC domains and relevant standards | Control matrix (ITGC domain × control × owner) |
| **Testing** | Execute test procedures (inquiry, observation, inspection, re-performance) | Test workpapers with evidence |
| **Deficiency evaluation** | Assess severity (deficiency, significant deficiency, material weakness) | Deficiency summary with risk rating |
| **Reporting** | Communicate findings to management with remediation recommendations | Audit report with management responses |

### 3.2 Evidence Types

| Evidence Type | Description | Example |
|---|---|---|
| **Inquiry** | Interviews with control owners | "Walk me through how a new user account is created" |
| **Observation** | Watching a control being performed | Observing the change approval board meeting |
| **Inspection** | Reviewing documentation or system configurations | Examining Active Directory password policy settings |
| **Re-performance** | Independently executing the control | Re-running an access review to verify completeness |

> **Advisory insight:** In SOX engagements, re-performance provides the highest level of assurance but is also the most resource-intensive. For advisory engagements (non-attestation), a combination of inquiry + inspection is typically sufficient for initial assessments.

---

## 4. ITGC Mapping to Frameworks

| ITGC Domain | ISO 27001 Annex A | COBIT 2019 | NIST CSF | SOX / ISAE 3402 |
|---|---|---|---|---|
| Access Controls | A.9.1–9.4 | DSS05, DSS06 | PR.AC | CC6.1–6.3 |
| Change Management | A.12.1.2, A.14.2 | BAI06, BAI07 | PR.IP-3 | CC8.1 |
| IT Operations | A.12.1, A.12.3, A.17 | DSS01, DSS02, DSS04 | PR.IP, PR.MA, DE.CM | CC7.1–7.4 |
| SDLC | A.14.1, A.14.2 | BAI03, BAI06 | PR.IP-2 | CC8.1 |

> This mapping demonstrates that ITGC domains are not framework-specific — they represent universal control objectives that appear across all major standards. An auditor or advisor fluent in one framework can translate findings to any other.

---

## 5. Common ITGC Deficiencies

Based on industry patterns and observations from the BSI and CGT case studies:

| # | Deficiency | ITGC Domain | Risk Impact | Observed In |
|---|---|---|---|---|
| 1 | No formal access provisioning/deprovisioning process | Access Controls | Unauthorized access to sensitive data | BSI |
| 2 | Privileged accounts shared or undocumented | Access Controls | Untraceable administrative actions | BSI |
| 3 | No change management process for infrastructure | Change Management | Uncontrolled changes introducing vulnerabilities | BSI, CGT |
| 4 | No security testing in SDLC | SDLC | Vulnerabilities deployed to production | CGT |
| 5 | Backup recovery never tested | IT Operations | Recovery failure during actual incident | BSI |
| 6 | No centralized logging or monitoring | IT Operations | Incidents undetected or unattributable | BSI, CGT |
| 7 | End-of-life systems in production | IT Operations | Unpatched vulnerabilities, no vendor support | BSI |
| 8 | No segregation of duties in IT | Access Controls | Single point of failure/fraud | BSI |

---

## 6. ITGC in the Context of Financial Audit (SOX / ISAE 3402)

In a financial audit context, ITGCs are evaluated because **automated controls in financial applications depend on the IT environment being reliable**. If ITGCs are deficient, the auditor cannot rely on application controls, which increases the scope and cost of substantive testing.

### The ITGC → Application Control → Financial Statement Chain

```
ITGC (environment-level)
  └── Application Controls (transaction-level)
       └── Financial Statement Assertions (completeness, accuracy, validity)
```

**Example:** If BSI's TAS-GL (General Ledger) automatically calculates depreciation, the auditor needs assurance that:
1. **Access controls** prevent unauthorized modification of depreciation parameters (ITGC)
2. **Change management** ensures any updates to the calculation logic are authorized and tested (ITGC)
3. **The application control** correctly applies the depreciation formula (Application Control)
4. **The financial statement** accurately reflects the depreciation expense (Assertion)

If ITGC testing reveals that anyone with network access can modify TAS-GL parameters (no access control), the auditor cannot rely on the automated depreciation calculation — regardless of whether the formula itself is correct.

> **PwC/EY relevance:** This is the core of "supportare la revisione contabile integrata attraverso l'analisi dei controlli ITGC, application controls, e interfacce" — exactly what the job descriptions require.

---

## 7. Practical Application: BSI ITGC Assessment Summary

[See case study: ISO27001 Risk-Management Project](../01-GRC-Case-Studies/iso27001-risk-management/README.md)

If engaged to perform an ITGC assessment at BSI, the following high-level findings would be expected:

| Domain | Maturity | Key Finding | Recommended Action |
|---|---|---|---|
| Access Controls | **Ad hoc** | No formal provisioning process; AD on end-of-life platform; no periodic access reviews | Implement access management policy; migrate AD to supported platform (Q2 roadmap); establish quarterly access reviews |
| Change Management | **Non-existent** | No documented change process; server replacements planned without formal change control | Implement change management policy before Q2 infrastructure changes |
| IT Operations | **Partial** | Backup regime exists but untested; no monitoring/SIEM; no incident management process | Test backup recovery; implement centralized logging (Q3-Q4 roadmap) |
| SDLC | **N/A** | BSI does not develop software; focus on vendor management for packaged applications | Implement vendor patch management policy (aligned with A.12.6.1) |

---

## 8. Practical Application: CGT ITGC Assessment Summary

[See case study: Cybersecurity Program Development](../01-GRC-Case-Studies/cybersecurity-program-development/README.md)

| Domain | Maturity | Key Finding | Recommended Action |
|---|---|---|---|
| Access Controls | **Partial** | Strong physical controls; no formal logical access management for application servers | Implement role-based access control policy; document privileged access |
| Change Management | **Partial** | SDLC exists for game development; no change management for IT infrastructure | Extend change management to SysOps/NetOps/ServOps operations |
| IT Operations | **Partial** | ManageIT provides monitoring; no formal incident management; BCP designed but not tested | Implement incident response procedures; conduct tabletop exercises |
| SDLC | **Partial** | Formal dev/test workflow; no security testing, code review, or secure coding standards | Embed security requirements; hire Application Security Specialist |

---

## References

- **ISO/IEC 27001:2022** — Annex A controls referenced throughout
- **COBIT 2019** — Process references for IT governance alignment
- **NIST Cybersecurity Framework (CSF)** — Function/category mapping
- **ISACA ITAF** — IT Audit Framework for testing methodology
- **SOX Section 404** — ITGC requirements for financial reporting reliability
- **ISAE 3402** — Assurance reports on controls at service organizations

---

*This document is part of the [Cybersecurity GRC & IT Audit Portfolio](../../README.md) — Project 03: Auditing & Monitoring.*
