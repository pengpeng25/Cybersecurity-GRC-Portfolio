# 01 — AI Inventory

> **SimulFlow S.r.l.** *(Fictional Organization)*
> B2B SaaS · AI-powered workflow automation & knowledge management · ~650 employees · Milan, Italy
> Primary Cloud: **Microsoft Azure** · Secondary: **AWS (DR)**
> Governance Frameworks: ISO/IEC 42001 · NIST AI RMF · ISO/IEC 27001 · SOC 2 Type II

---

## AI System Registry

| AI ID | System | Type | Vendor | Deployment | Owner | Criticality | Risk Rating | Status |
|-------|--------|------|--------|------------|-------|-------------|-------------|--------|
| AI-001 | SimulFlow Assistant | Generative LLM | Azure OpenAI | Azure EU West | Product | 🔴 High | 🔴 High | Approved |
| AI-002 | SimulFlow Knowledge Hub | RAG System | Azure AI Search + OpenAI | Azure | Knowledge Mgmt | 🔴 High | 🔴 High | Approved |
| AI-003 | SimulFlow Workflow Copilot | AI Agent | Microsoft Copilot Studio | Azure | Operations | 🔴 High | 🔴 High | Approved |
| AI-004 | Developer Coding Assistant | Code Generation LLM | GitHub Copilot Enterprise | SaaS | Engineering | 🟡 Medium | 🟡 Medium | Approved |
| AI-005 | AI Translation API | Third-Party AI API | DeepL API | SaaS API | Customer Success | 🟡 Medium | 🟡 Medium | Approved w/ Restrictions |
| AI-006 | Meeting Intelligence Assistant | Speech-to-Text + GenAI | Microsoft Teams Premium | Microsoft 365 | Human Resources | 🟡 Medium | 🟡 Medium | ⚠️ Pilot |

---

## System Details

### AI-001 · SimulFlow Assistant
| Field | Detail |
|-------|--------|
| Purpose | Customer-facing assistant for workflow guidance and product documentation |
| Data Classification | Internal / Confidential |
| Personal Data | ⚠️ Limited — user account information |
| Customer Data | ✅ Yes |
| Risk Rationale | External-facing LLM handling customer data; high exposure to prompt injection and sensitive information disclosure |

### AI-002 · SimulFlow Knowledge Hub
| Field | Detail |
|-------|--------|
| Purpose | Internal enterprise knowledge search across policies, SOPs, and technical documentation |
| Data Classification | Confidential |
| Personal Data | ❌ No |
| Customer Data | ❌ No |
| Risk Rationale | RAG architecture introduces data poisoning and retrieval manipulation risks against confidential internal content |

### AI-003 · SimulFlow Workflow Copilot
| Field | Detail |
|-------|--------|
| Purpose | Generate and automate internal business workflows |
| Data Classification | Confidential |
| Personal Data | ⚠️ Limited |
| Customer Data | ⚠️ Partial — workflow metadata only |
| Risk Rationale | Agentic system with workflow execution permissions; elevated risk of excessive agency and unauthorized action |

### AI-004 · Developer Coding Assistant
| Field | Detail |
|-------|--------|
| Purpose | Assist developers with code generation and documentation |
| Data Classification | Internal |
| Personal Data | ❌ No |
| Customer Data | ❌ No |
| Risk Rationale | Potential exposure of proprietary source code to third-party SaaS; supply chain trust dependency on GitHub/Microsoft |

### AI-005 · AI Translation API
| Field | Detail |
|-------|--------|
| Purpose | Translate multilingual customer support tickets |
| Data Classification | Confidential |
| Personal Data | ⚠️ Possible — customer support content may include PII |
| Customer Data | ✅ Yes |
| Risk Rationale | Third-party API processes customer data outside the organization's cloud perimeter; GDPR data transfer risk |

### AI-006 · Meeting Intelligence Assistant ⚠️ Pilot
| Field | Detail |
|-------|--------|
| Purpose | Generate meeting summaries and action items |
| Data Classification | Internal |
| Personal Data | ✅ Yes — voice recordings, names, discussion content |
| Customer Data | ❌ No |
| Risk Rationale | HR-owned system in pilot phase processing employee personal data including audio; highest GDPR exposure in portfolio; governance controls not yet fully established |

---

## Classification Reference

### AI System Types
| Type | Definition | Systems |
|------|------------|---------|
| Generative LLM | Generates natural language responses | AI-001 |
| RAG System | Retrieves enterprise knowledge before generation | AI-002 |
| AI Agent | Executes or orchestrates business workflows autonomously | AI-003 |
| Code Assistant | Supports software development via code generation | AI-004 |
| Third-Party AI API | External AI service integrated through APIs | AI-005 |
| Productivity AI | AI embedded in office tools | AI-006 |

### Data Classification Scheme
| Level | Description | Example |
|-------|-------------|---------|
| Public | Approved for public release | Product documentation |
| Internal | Routine internal business information | Meeting notes |
| Confidential | Sensitive business information | Contracts, SOPs |
| Restricted | Requires enhanced protection | Customer PII, auth secrets |

### Risk Rating Criteria
| Rating | Triggers |
|--------|----------|
| 🔴 High | External-facing **or** processes customer data **or** agentic execution capability |
| 🟡 Medium | Internal use **and** limited personal data **and** human-in-the-loop |
| 🟢 Low | No personal/customer data, read-only, internal audience only |

### AI Lifecycle Status
| Status | Description |
|--------|-------------|
| Proposed | Requested, not yet assessed |
| Under Review | Risk assessment in progress |
| Approved | Cleared for production use |
| Approved w/ Restrictions | Approved with compensating controls |
| ⚠️ Pilot | Limited deployment — full governance controls pending |
| Retired | No longer in use |

---

## Portfolio Linkage

This inventory serves as the **single source of truth** across the AI Governance Program:

| Document | How it references this inventory |
|----------|----------------------------------|
| [02-AI-Risk-Assessments](02-AI-Risk-Assessments.md) | Selects systems (AI-001, AI-002, AI-003) for detailed threat modelling |
| [03-AI-Risk-Register](/03-AI-Risk-Register.md) | Each risk entry is linked to one or more AI IDs |
| [05-ISO42001-Gap-Assessment](/05-ISO42001-Gap-Assessment.md) | Verifies governance metadata (owner, classification, approval) per system |
| [06-Vendor-Risk-Assessment](/06-Vendor-Risk-Assessment.md) | Draws vendor list directly from this inventory (Azure OpenAI, GitHub, DeepL) |
| [08-Executive-Dashboard](/08-Dashboard.md) | Aggregates risk ratings and approval status for leadership reporting |

---

*Last updated: 2026-06-26*
