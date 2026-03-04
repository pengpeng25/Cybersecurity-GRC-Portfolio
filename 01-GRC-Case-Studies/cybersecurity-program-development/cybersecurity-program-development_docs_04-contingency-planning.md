# 04 — Cybersecurity Contingency Planning Program

[← Back to Project Overview](../README.md)

---

## Executive Summary

CGT's intellectual property (game source code) and 24/7 operations lack formal cyber contingency policies. Current resilience is limited to physical security (Ironclad) and backup infrastructure (SAN + cloud). There is no incident response plan, no disaster recovery procedure, and no business continuity strategy.

**Objective:** Transition from reactive physical security to proactive digital resilience through a structured Contingency Planning (CP) lifecycle.

## CP Lifecycle Overview

The program follows a **4-phase lifecycle**:

```
Phase 1: Governance → Phase 2: Analysis → Phase 3: Implementation → Phase 4: Readiness
                                                                          ↺ (continuous)
```

| Phase | Focus | Key Question |
|---|---|---|
| **Phase 1** | Governance & Policy | "Who is in charge and what are the rules?" |
| **Phase 2** | Business Impact Analysis | "What matters most and how badly does downtime hurt?" |
| **Phase 3** | Implementation | "What do we do when something goes wrong?" |
| **Phase 4** | Readiness & Validation | "Does our plan actually work?" |

---

## Phase 1: Governance & Policy Development

### Committees

| Committee | Composition | Authority |
|---|---|---|
| **Contingency Planning Management Team (CPMT)** | CISO (chair), COO, CIO, CBO, HR Manager | Executive oversight, funding authorization, strategic direction |
| **Subordinate Team Leaders** | IR Lead, DR Lead, BC Lead | Tactical planning within their domains |

### Key Deliverables

#### 1. CPMT Charter
- Defines the CPMT's authority, scope, and reporting obligations
- Establishes funding authority for contingency resources
- Mandates quarterly review of CP program status

#### 2. CP Policy Statement
The "constitution" of CGT's contingency planning:

| Element | Detail |
|---|---|
| **Mandate** | All CGT divisions must comply with contingency planning requirements |
| **Authority** | CISO has operational authority during declared security incidents |
| **Scope** | Covers all information systems, data assets, and supporting infrastructure |
| **Roles** | Defines responsibilities for CPMT members and subordinate teams |
| **Review** | Annual review or upon significant organizational/threat changes |

---

## Phase 2: Business Impact Analysis (BIA)

### Committee
- CPMT + Subordinate Team Leaders

### Objective
Quantify the financial and operational impact of system outages to establish recovery priorities.

### Prioritized Criticality List

| Tier | Asset | RTO | Justification |
|---|---|---|---|
| **Tier 0** | Rack 2 — Game Source Code (DevelopIT) | **4 hours** | Core IP; active development; any loss threatens product pipeline and competitive position |
| **Tier 0** | Rack 3 — SAN Backups | **4 hours** | Recovery capability for all other assets; if backups fail, nothing else can be restored |
| **Tier 1** | Rack 1 — Corporate Applications | **8 hours** | Financial, HR, and client support systems; operational but not existential |
| **Tier 1** | Network Infrastructure (Firewalls, VPN, Switches) | **4 hours** | All systems depend on network connectivity |
| **Tier 2** | Racks 6–15 — Testing Environments | **24 hours** | Important for product cycle but can tolerate longer downtime |
| **Tier 2** | Cloud Backup Service | **48 hours** | Last-resort recovery; not needed if SAN is operational |

### BIA Key Finding
> A total development outage (Rack 2 + Rack 3) would halt all active game development, potentially delaying product releases worth millions in revenue. The 4-hour RTO reflects the maximum tolerable downtime before financial impact becomes material.

---

## Phase 3: Implementation

### Three Specialized Teams

| Team | Mission | Composition |
|---|---|---|
| **Incident Response (IR)** | Detect, contain, and eradicate security incidents | Security Analyst (lead), Security Engineer, NetOps representative |
| **Disaster Recovery (DR)** | Restore systems and data after a major disruption | ServOps lead, SysOps representative, Security Architect |
| **Business Continuity (BC)** | Maintain critical business operations during extended outages | COO (sponsor), department managers, HR representative |

### Technical Protocols

| Protocol | Description | Target Scenario |
|---|---|---|
| **Ransomware Response Policy** | Isolate affected systems, assess encryption scope, activate backup recovery, notify CPMT | Ransomware targeting Rack 1 or Rack 2 |
| **Cloud Failover Protocol** | Activate cloud storage provider as warm site for critical systems | Data center physical disaster (fire, flood) |
| **Network Recovery Procedure** | Restore firewall, VPN, and switch configurations from documented baselines | Network infrastructure failure |

### Resource Requirement Map

| Recovery Effort | Required Resources | Board Priority Alignment |
|---|---|---|
| Source code recovery | SAN restoration + cloud backup access | Protect IP (highest priority) |
| Corporate systems recovery | Server rebuild + NAS restoration | Maintain operations |
| Network recovery | Firewall/VPN configuration restore | Enable all other recovery |
| Testing environment recovery | VM rebuild from cloud backups | Resume product development cycle |

### Hardened Defenses (New)

| Defense | Current State | Target State |
|---|---|---|
| Offsite backups | Weekly to cloud provider | Automated daily encrypted backups |
| Firewall redundancy | Single Check Point 4800 | Redundant firewall pair (active/passive) |
| Monitoring | ManageIT (basic) | ManageIT + SIEM integration |

### "Red Books" — Standard Operating Procedures

Step-by-step recovery SOPs for critical scenarios:

| Red Book | Scope | Key Steps |
|---|---|---|
| **NAS Restoration** | SAN and NAS recovery | Verify backup integrity → restore to clean hardware → validate data → reconnect to network |
| **VPN Recovery** | Corporate VPN restoration | Deploy backup VPN configuration → verify authentication → test remote access |
| **Corporate Switch Recovery** | Network switch restoration | Load baseline configuration → verify VLAN assignments → test connectivity to all racks |

### Contact & Escalation Tree

```
Incident Detected
    → Security Analyst (first responder)
        → CISO (incident commander)
            → COO (business impact decisions)
                → CEO (external communications, legal)
                    → Board (if material impact)
```

---

## Phase 4: Validation & Continuous Improvement

### Testing, Training & Exercises (TT&E)

| Activity | Frequency | Participants |
|---|---|---|
| **Tabletop Simulation** | Bi-annually | CPMT + all team leads |
| **Functional Exercise** | Annually | IR/DR/BC teams |
| **Full-Scale Exercise** | Every 2 years | All staff |
| **Backup Restore Test** | Quarterly | ServOps + DR team |

### Example Tabletop Scenario
> **Data Center Flood:** A burst pipe floods Room 127 (data center). Rack 1 and Rack 2 are offline. SAN (Rack 3) is partially damaged. Cloud backups are available but last full backup was 5 days ago. Walk through the response.

### After-Action Reports (AAR)
- Document lessons learned from every exercise and real incident
- Update Red Books and escalation procedures based on findings
- Feed improvements back into Phase 1 governance review

### Annual Program Audit
- Review CP program against current threat landscape
- Update BIA as CGT expands (especially Racks 6–15 for new game testing)
- Validate RTO/RPO targets remain appropriate

---

*Previous: [← Policy Framework](./03-policy-framework.md) | Next: [Governance Model →](./05-governance-model.md)*
