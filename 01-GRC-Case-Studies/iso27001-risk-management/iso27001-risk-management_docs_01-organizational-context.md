# 01 — Organizational Context

[← Back to Project Overview](../README.md)

---

## Company Profile

**Business Supplies, Inc. (BSI)** is a regional office supply retailer established in 1979. The company operates:

- **5 regional stores** across the north Atlantis region
- **1 corporate headquarters** serving as the central shipping and receiving hub
- **A fleet of 20 delivery trucks** supporting distribution operations
- **An e-commerce platform** (TERP-Web) for online sales

BSI's mission is to provide high-quality business and technology supplies, equipment, furnishings, and advice to maximize customer business operations.

## Leadership Transition

In 2019, co-founders William Billingsley Sr. and Alexander Boscovitch retired, leaving **William Billingsley II ("Junior")** as CEO. Junior holds an MBA and BSBA in Entrepreneurship with a minor in IT. His priorities:

1. ✅ Modernize the IT infrastructure and telephony systems (completed)
2. 🔄 **Improve information security at corporate headquarters** (this engagement)

## Executive Structure

| Role | Name | Responsibility |
|------|------|---------------|
| CEO | William Billingsley Jr. | Overall operations, all stores and HQ |
| COO | Grace Williams | Corporate and branch operations, sales, procurement, distribution |
| CFO | Rachel Xieng | All financial operations |
| IT Manager | Cecilia Thompson | IT infrastructure (2-person team) |

## Current Security Posture — Gap Analysis

BSI's security maturity is **informal and reactive**. The following critical gaps were identified:

| Gap | Risk Implication |
|-----|-----------------|
| **No formal Information Security Policy** | No documented standards for data handling, access control, or incident response |
| **No dedicated security personnel** | IT team of 2 (networks + systems) — no security specialization |
| **No structured risk register** | Risks are neither identified, assessed, nor tracked |
| **Aging infrastructure** | Servers A and B (Active Directory, DNS) running end-of-life hardware |
| **No compliance validation** | PCI data (e-commerce), PII/medical data (HR) — no formal audit or controls |
| **No recurring executive security review** | No governance mechanism for security oversight |

## IT Infrastructure Summary

BSI operates a centralized data center (Room 127) at corporate headquarters:

- **2 full-height server racks** with 12 servers total
- **2 NAS devices** for on-site backup with cross-replication
- **Weekly cloud backup** to an external SaaS provider
- **Wired Ethernet network only** — no wireless deployment
- **Key systems:** Active Directory, Exchange email, Traverse ERP/Accounting/Distribution, HRIS, IIS web services

## Why ISO/IEC 27001?

ISO 27001 was selected as the governing framework for the following reasons:

| Factor | Rationale |
|--------|-----------|
| **Risk-based governance** | Ensures investment is directed toward high-impact risk areas — critical for a resource-constrained organization |
| **Executive accountability** | Requires formal risk ownership and management review cycles — addresses BSI's governance gap |
| **Structured ISMS** | Provides a systematic approach to managing sensitive information — replaces BSI's ad-hoc practices |
| **Certification capability** | Auditable certification supports competitive positioning for high-value contracts |
| **Business integration** | Unlike purely technical frameworks, ISO 27001 embeds security governance into business operations |

## ISMS Scope Statement

The Information Security Management System (ISMS) scope covers:

- **In scope:** All information assets, systems, and processes at BSI Corporate Headquarters, including the data center (Room 127), all server infrastructure, network systems, and business applications supporting financial, HR, sales, distribution, and e-commerce operations.
- **Out of scope (Phase 1):** Regional store IT systems, delivery fleet onboard systems, and employee personal devices. These will be considered for inclusion in subsequent ISMS expansion phases.

---

*Next: [Risk Assessment Methodology →](./02-risk-assessment-methodology.md)*
