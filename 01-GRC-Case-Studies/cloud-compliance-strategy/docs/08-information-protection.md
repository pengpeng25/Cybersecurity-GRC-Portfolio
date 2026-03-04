# Information Protection and Data Lifecycle

[← Back to Overview](../README.md) | [← Previous: Insider Risk Management](07-insider-risk-management.md) | [Next: Documentation & Reporting →](09-documentation-reporting.md)

## Overview

Effective information protection and data lifecycle management are essential for NexaGlobal Ltd. to safeguard sensitive data and meet regulatory requirements. This section covers **data classification**, **protection policies**, and **lifecycle management** using Microsoft Azure and Microsoft 365 tools.

---

## 1. Azure Information Protection (AIP) / Microsoft Purview Information Protection

### Purpose

**Microsoft Purview Information Protection** (formerly Azure Information Protection) enables organizations to discover, classify, and protect sensitive information wherever it lives or travels.

### Key Capabilities

- **Data Discovery**: Automatically scan and identify sensitive data across Microsoft 365, Azure, and on-premises systems
- **Classification**: Apply sensitivity labels manually or automatically based on content
- **Protection**: Encrypt files, apply access restrictions, and add watermarks
- **Tracking**: Monitor how labeled documents are used and shared
- **User Guidance**: Provide real-time recommendations to users on data handling

---

## 2. Data Classification Strategy

### Sensitivity Labels

**Objective**: Establish a clear, organization-wide taxonomy for classifying data based on sensitivity and business impact.

### Proposed Classification Scheme for NexaGlobal

| Label | Description | Examples | Protection Actions |
|-------|-------------|----------|-------------------|
| **Public** | Information intended for public disclosure | Marketing materials, press releases, public website content | No encryption; watermark optional |
| **Internal** | Information for internal use only | Internal memos, project plans, non-sensitive reports | No encryption; restrict external sharing |
| **Confidential** | Sensitive business information | Financial reports, customer lists, strategic plans | Encrypt; restrict to authorized users; audit access |
| **Highly Confidential** | Critical assets requiring maximum protection | Intellectual property, M&A documents, executive communications | Encrypt; restrict to specific users/groups; prevent copying/printing; audit all access |

---

### Classification Process

#### Automatic Classification

**Triggers**: Content-based rules automatically apply labels when sensitive data is detected.

**Example Rules**:
- **Credit Card Numbers**: If document contains 16-digit numbers matching credit card patterns → Label as "Confidential"
- **Social Security Numbers**: If document contains SSN patterns → Label as "Highly Confidential"
- **Keywords**: If document contains "Trade Secret," "Proprietary," or "Confidential" → Label as "Confidential"
- **Intellectual Property**: If document is stored in `/IP_Documentation/` folder → Label as "Highly Confidential"

**Implementation**:
- Configure **auto-labeling policies** in Microsoft 365 Compliance Center
- Use **trainable classifiers** (machine learning models) to detect sensitive content types (e.g., source code, financial statements)
- Test policies in **simulation mode** before enforcing to avoid false positives

#### Manual Classification

**User Responsibility**: Users can manually apply labels when creating or editing documents.

**User Guidance**:
- **Policy Tips**: Real-time recommendations appear when users create documents with sensitive content
  - Example: "This document contains financial data. Consider labeling it as 'Confidential.'"
- **Mandatory Labeling**: Require users to apply a label before saving or sending documents
- **Justification**: Prompt users to provide a reason when downgrading a label (e.g., from "Confidential" to "Internal")

---

## 3. Protection Policies

### Encryption

**Objective**: Protect data at rest and in transit using encryption.

#### At Rest
- **Azure Storage**: All storage accounts use **Azure Storage Service Encryption (SSE)** with Microsoft-managed or customer-managed keys
- **Azure SQL Database**: Enable **Transparent Data Encryption (TDE)** for all databases
- **Microsoft 365**: Files in OneDrive and SharePoint are encrypted at rest by default

#### In Transit
- **TLS 1.2+**: All data transfers use TLS 1.2 or higher
- **Azure VPN**: Use Azure VPN Gateway or ExpressRoute for secure on-premises connectivity
- **Private Endpoints**: Use Azure Private Link to access Azure services over private network

#### Rights Management

**Azure Rights Management (Azure RMS)**: Integrated with sensitivity labels to enforce granular access controls.

**Protection Actions by Label**:

| Label | Encryption | Permissions | Additional Controls |
|-------|-----------|-------------|---------------------|
| **Public** | None | Full control for all users | None |
| **Internal** | None | Full control for internal users; block external sharing | Watermark: "Internal Use Only" |
| **Confidential** | Yes | View, Edit for authorized users; block Copy, Print | Watermark: "Confidential"; audit all access |
| **Highly Confidential** | Yes | View-only for specific users/groups; block Copy, Print, Forward | Watermark: "Highly Confidential"; expire access after 90 days; audit all access |

---

### Data Loss Prevention (DLP)

**Objective**: Prevent sensitive data from leaving the organization through unauthorized channels.

#### DLP Policies for NexaGlobal

| Policy | Scope | Conditions | Actions |
|--------|-------|------------|---------|
| **Block External Sharing of IP** | OneDrive, SharePoint, Teams | Document labeled "Highly Confidential" | Block external sharing; notify user and admin |
| **Prevent Credit Card Leaks** | Email, Teams | Message contains credit card numbers | Block send; notify user with policy tip |
| **Restrict Financial Data** | Email | Attachment labeled "Confidential" + recipient is external | Require manager approval before sending |
| **USB Device Control** | Endpoints | User attempts to copy "Highly Confidential" file to USB | Block action; alert security team |

**Implementation**:
- Configure DLP policies in **Microsoft 365 Compliance Center**
- Apply policies to **Exchange Online** (email), **SharePoint/OneDrive** (files), **Teams** (chats/files), and **Endpoints** (devices)
- Use **policy tips** to educate users in real-time (e.g., "This message contains sensitive data and cannot be sent externally")
- Enable **incident reports** to track DLP violations and trends

---

### User Education

**Objective**: Foster a culture of security mindfulness by guiding users on proper data handling.

#### Real-Time Guidance

**Policy Tips**: Appear when users attempt risky actions.
- Example: User tries to email a "Confidential" document to an external address → Policy tip: "This document is confidential. External sharing is restricted. Contact your manager for approval."

**Justification Prompts**: Require users to explain why they're downgrading a label or overriding a DLP policy.
- Example: User changes label from "Confidential" to "Internal" → Prompt: "Why are you downgrading this label? (Required for audit trail)"

#### Training Programs

- **Onboarding**: All new employees complete data classification training
- **Quarterly Refreshers**: Email campaigns with examples of proper and improper data handling
- **Simulated Incidents**: Test users with simulated DLP violations (e.g., fake phishing email with sensitive attachment) and provide feedback

---

## 4. Data Lifecycle Management

### Azure Blob Storage Lifecycle Management

**Purpose**: Automate data transitions between storage tiers and eventual deletion based on age and access patterns.

### Storage Tiers

| Tier | Use Case | Cost | Access Latency |
|------|----------|------|----------------|
| **Hot** | Frequently accessed data | Highest storage cost, lowest access cost | Milliseconds |
| **Cool** | Infrequently accessed data (accessed < 1/month) | Lower storage cost, higher access cost | Milliseconds |
| **Archive** | Rarely accessed data (long-term retention) | Lowest storage cost, highest access cost | Hours (rehydration required) |

---

### Lifecycle Policies for NexaGlobal

**Objective**: Optimize storage costs while meeting regulatory retention requirements.

#### Policy Examples

| Data Type | Retention Requirement | Lifecycle Policy |
|-----------|----------------------|------------------|
| **Financial Records** | 7 years | Hot (0-90 days) → Cool (91 days - 2 years) → Archive (2-7 years) → Delete (after 7 years) |
| **Customer Personal Data** | 5 years or until deletion request | Hot (0-180 days) → Cool (181 days - 5 years) → Delete (after 5 years or upon request) |
| **Intellectual Property** | Indefinite | Hot (0-365 days) → Cool (1-5 years) → Archive (5+ years) |
| **Marketing Materials** | 3 years | Hot (0-90 days) → Cool (91 days - 3 years) → Delete (after 3 years) |
| **Temporary/Cache Data** | 30 days | Hot (0-30 days) → Delete (after 30 days) |

#### Implementation

**Azure Portal**:
1. Navigate to Storage Account → **Lifecycle Management**
2. Add rule: "Transition financial records to Cool tier after 90 days"
3. Add rule: "Transition financial records to Archive tier after 2 years"
4. Add rule: "Delete financial records after 7 years"

**Automation**:
- Lifecycle policies run **daily** and automatically transition or delete blobs based on last modified date
- No manual intervention required once policies are configured

---

### Microsoft 365 Retention Policies

**Purpose**: Retain or delete content in Microsoft 365 (email, files, Teams chats) based on organizational and regulatory requirements.

#### Retention Policies for NexaGlobal

| Content Type | Retention Period | Action After Retention |
|--------------|------------------|------------------------|
| **Email (All Users)** | 7 years | Delete |
| **Email (Executives)** | 10 years | Delete |
| **OneDrive/SharePoint (Financial)** | 7 years | Delete |
| **OneDrive/SharePoint (General)** | 3 years | Delete |
| **Teams Chats** | 1 year | Delete |
| **Teams Channel Messages** | 3 years | Delete |

**Implementation**:
- Configure retention policies in **Microsoft 365 Compliance Center**
- Apply policies to specific locations (e.g., all mailboxes, specific SharePoint sites)
- Use **retention labels** for exceptions (e.g., legal hold for litigation)

---

### Periodic Reviews

**Recommendation**: Conduct **quarterly reviews** of lifecycle policies to ensure alignment with:
- **Regulatory Changes**: New retention requirements (e.g., updated GDPR guidance)
- **Business Needs**: New data types or use cases
- **Cost Optimization**: Identify opportunities to transition data to cheaper tiers sooner

**Review Process**:
1. **Assess Current Policies**: Review all lifecycle and retention policies
2. **Analyze Storage Costs**: Identify high-cost storage accounts and opportunities for optimization
3. **Verify Compliance**: Ensure policies meet all regulatory requirements
4. **Update Policies**: Modify policies as needed
5. **Communicate Changes**: Notify stakeholders of policy updates

---

## 5. Data Subject Rights (GDPR, CCPA)

### Right to Access

**Requirement**: Provide individuals with a copy of their personal data upon request.

**Implementation**:
- Use **Microsoft 365 Content Search** or **eDiscovery** to locate all instances of an individual's data
- Export data in a portable format (e.g., CSV, JSON)
- Deliver to data subject within 30 days (GDPR requirement)

### Right to Erasure ("Right to be Forgotten")

**Requirement**: Delete an individual's personal data upon request (with certain exceptions).

**Implementation**:
- Use **Content Search** to identify all instances of the individual's data
- Use **retention policies** to ensure data is not retained beyond legal requirements
- Permanently delete data from all systems (including backups)
- Document deletion for audit trail

### Right to Rectification

**Requirement**: Correct inaccurate personal data upon request.

**Implementation**:
- Locate data using Content Search
- Update records in source systems (CRM, databases, etc.)
- Verify corrections propagate to all downstream systems

---

## Benefits to NexaGlobal Ltd.

| Area | Benefit |
|------|---------|
| **Data Protection** | Encryption and access controls prevent unauthorized access to sensitive data |
| **Compliance** | Automated classification and retention policies ensure GDPR, HIPAA, and SOC 2 compliance |
| **Cost Optimization** | Lifecycle management reduces storage costs by transitioning data to cheaper tiers |
| **User Awareness** | Real-time guidance and policy tips educate users on proper data handling |
| **Audit Readiness** | Comprehensive tracking and logging simplify audit preparation |

---

## Tools Summary

- **Microsoft Purview Information Protection**: Data classification and protection
- **Azure Rights Management (Azure RMS)**: Encryption and access control
- **Data Loss Prevention (DLP)**: Prevent unauthorized data sharing
- **Azure Blob Storage Lifecycle Management**: Automated data tiering and deletion
- **Microsoft 365 Retention Policies**: Content retention and deletion
- **Content Search / eDiscovery**: Data subject rights fulfillment
- **Trainable Classifiers**: Machine learning-based content detection

---

**Next**: [Documentation & Reporting →](09-documentation-reporting.md)
