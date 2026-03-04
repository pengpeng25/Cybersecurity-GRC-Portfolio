# Insider Risk Management

[← Back to Overview](../README.md) | [← Previous: Compliance Management](06-compliance-management.md) | [Next: Information Protection →](08-information-protection.md)

## Overview

Insider threats—whether malicious or unintentional—pose significant risks to NexaGlobal Ltd.'s digital assets. This section outlines a comprehensive strategy for detecting, investigating, and mitigating insider risks using Microsoft's suite of security tools.

---

## 1. Insider Risk Management Strategy

### Core Principles

**Objective**: Recognize that insider threats manifest differently than external threats and require specialized detection and response approaches.

**Key Tenets**:
1. **Privacy-First**: Balance security monitoring with employee privacy rights
2. **Context-Aware**: Consider user role, access level, and behavioral patterns
3. **Graduated Response**: Escalate from monitoring → alerting → investigation → action based on risk severity
4. **Continuous Improvement**: Refine detection algorithms based on false positives and missed threats

---

## 2. Microsoft Insider Risk Management

### Purpose

**Microsoft Insider Risk Management** (part of Microsoft 365 Compliance Center) uses machine learning and behavioral analytics to identify potentially risky activities.

### Key Capabilities

- **Risk Indicators**: Detects anomalous behaviors such as:
  - Unusual file downloads or deletions
  - Copying data to personal cloud storage
  - Accessing sensitive data outside normal work hours
  - Emailing large volumes of data to external addresses
  - Searching for sensitive keywords (e.g., "confidential," "merger")
- **Policy Templates**: Pre-built policies for common scenarios (departing employees, data leaks, security violations)
- **Integrated Workflows**: Case management, investigation tools, and escalation paths
- **Privacy Controls**: Pseudonymization of user identities until investigation is warranted

---

### Implementation for NexaGlobal

#### Step 1: Define Risk Policies

**Policy Templates**:

| Policy | Description | Indicators |
|--------|-------------|------------|
| **Data Theft by Departing Users** | Detect employees exfiltrating data before resignation | Unusual file downloads, copying to USB, emailing to personal accounts |
| **General Data Leaks** | Identify unintentional or malicious data exposure | Sharing sensitive files externally, uploading to unauthorized cloud services |
| **Security Policy Violations** | Flag violations of acceptable use policies | Accessing prohibited websites, installing unauthorized software |
| **Offensive Language** | Detect harassment or hostile communications | Scanning emails and chats for offensive keywords |

**Custom Policy for NexaGlobal**:
- **Intellectual Property Protection**: Alert when users access IP documentation outside their normal role or download large volumes of proprietary files

#### Step 2: Continuous Monitoring

**Data Sources**:
- **Microsoft 365**: Email, OneDrive, SharePoint, Teams
- **Azure AD**: Sign-in logs, risky sign-ins, conditional access failures
- **Endpoints**: File activity, USB usage, application installations (via Microsoft Defender for Endpoint)

**Monitoring Approach**:
- **Real-Time Analysis**: Machine learning models analyze user activity continuously
- **Baseline Establishment**: System learns normal behavior patterns for each user over 30-60 days
- **Anomaly Detection**: Flags deviations from baseline (e.g., user who normally accesses 10 files/day suddenly downloads 500)

#### Step 3: Alert Thresholds

**Risk Scoring**:
- Each risky activity is assigned a **risk score** (0-100)
- Scores accumulate over time; high cumulative scores trigger alerts
- Thresholds can be adjusted to balance sensitivity and false positives

**Recommended Thresholds for NexaGlobal**:

| Risk Level | Score Range | Action |
|------------|-------------|--------|
| **Low** | 0-30 | Log for future reference; no immediate action |
| **Medium** | 31-60 | Alert security team; monitor user for 7 days |
| **High** | 61-85 | Initiate investigation; review user activity logs |
| **Critical** | 86-100 | Immediate investigation; consider access restrictions |

#### Step 4: Incident Response Protocols

**Investigation Workflow**:

1. **Alert Triggered**: Insider Risk Management generates alert
2. **Triage**: Security analyst reviews alert details and user context
3. **Evidence Gathering**: Collect relevant logs, emails, file access records
4. **Risk Assessment**: Determine if activity is malicious, negligent, or benign
5. **Escalation Decision**:
   - **Benign**: Close case, adjust policy to reduce false positives
   - **Negligent**: User training and warning
   - **Malicious**: Involve HR, legal, and potentially law enforcement
6. **Remediation**: Revoke access, recover data, implement additional controls
7. **Documentation**: Record findings and actions in case management system

**Notification Procedures**:
- **Security Team**: Immediate notification for high/critical alerts
- **HR**: Notified when investigation confirms policy violation
- **Legal**: Notified for potential criminal activity or regulatory violations
- **User**: Notified only after investigation concludes (to avoid tipping off malicious actors)

---

## 3. Microsoft Security Tools for Insider Risk

### Microsoft Defender for Identity

**Purpose**: Detect advanced threats targeting Active Directory.

**Insider Risk Use Cases**:
- **Suspicious Authentication**: Detect pass-the-hash, pass-the-ticket attacks
- **Lateral Movement**: Identify users accessing systems outside their normal scope
- **Privilege Escalation**: Flag attempts to gain unauthorized admin access
- **Reconnaissance**: Detect enumeration of users, groups, or resources

**NexaGlobal Implementation**:
- Deploy Defender for Identity sensors on domain controllers
- Integrate with Azure AD for hybrid identity protection
- Configure alerts for suspicious authentication patterns

---

### Microsoft Purview Information Protection (MIP)

**Purpose**: Classify and protect sensitive information to prevent data leaks.

**Insider Risk Use Cases**:
- **Prevent Unintentional Leaks**: Block users from emailing highly confidential documents to external addresses
- **Detect Intentional Exfiltration**: Alert when users attempt to remove sensitivity labels or copy protected files to USB drives
- **Audit Access**: Track who accessed sensitive documents and when

**NexaGlobal Implementation**:
- Apply sensitivity labels to intellectual property, financial records, and customer data
- Configure DLP policies to prevent external sharing of "Highly Confidential" documents
- Enable audit logging for all labeled documents

---

### Azure Active Directory (Azure AD)

**Purpose**: Identity and access management with built-in risk detection.

**Insider Risk Features**:
- **Conditional Access**: Block access from unusual locations or risky devices
- **Identity Protection**: Detect compromised credentials, atypical travel, anonymous IP usage
- **Access Reviews**: Periodic reviews to identify and remove excessive permissions

**NexaGlobal Implementation**:
- Enable **Azure AD Identity Protection** to detect risky sign-ins
- Configure **Conditional Access** policies:
  - Require MFA for access from new locations
  - Block access from high-risk countries
  - Require compliant devices for accessing sensitive data
- Conduct **quarterly access reviews** for privileged roles

---

### Microsoft Cloud App Security (MCAS) / Defender for Cloud Apps

**Purpose**: Cloud Access Security Broker (CASB) for monitoring and controlling cloud app usage.

**Insider Risk Use Cases**:
- **Shadow IT Detection**: Identify unauthorized cloud services (e.g., personal Dropbox, WeTransfer)
- **Anomalous Behavior**: Detect unusual data uploads, downloads, or sharing patterns
- **Compromised Accounts**: Identify accounts exhibiting signs of compromise (e.g., impossible travel, mass downloads)
- **Rogue Applications**: Flag OAuth apps with excessive permissions

**NexaGlobal Implementation**:
- Connect MCAS to Microsoft 365, Azure, and third-party SaaS apps
- Configure **anomaly detection policies** for unusual file activity
- Enable **app governance** to control OAuth app permissions
- Block access to high-risk cloud services via Conditional Access App Control

---

### Office 365 Audit Log

**Purpose**: Comprehensive logging of user and admin activities across Microsoft 365.

**Insider Risk Use Cases**:
- **Track File Access**: Who accessed, downloaded, or shared specific files
- **Monitor Email Activity**: Sent items, forwarded emails, deleted messages
- **Admin Actions**: Changes to permissions, mailbox access, policy modifications

**NexaGlobal Implementation**:
- Enable **unified audit logging** across all Microsoft 365 services
- Retain logs for **2 years** in Log Analytics
- Create **custom queries** to search for specific activities (e.g., "Show all file downloads by User X in the last 30 days")

---

### Office 365 Advanced Threat Protection (ATP) / Defender for Office 365

**Purpose**: Protect against phishing, malware, and malicious links in email and collaboration tools.

**Insider Risk Use Cases**:
- **Detect Compromised Accounts**: Identify accounts sending phishing emails or malware
- **Flag Suspicious Communications**: Detect emails with unusual attachments or links
- **Prevent Data Exfiltration**: Block emails containing sensitive data sent to suspicious external addresses

**NexaGlobal Implementation**:
- Enable **Safe Attachments** and **Safe Links** for all users
- Configure **anti-phishing policies** with impersonation protection
- Enable **mailbox intelligence** to detect unusual sending patterns

---

### Office 365 Communication Compliance

**Purpose**: Monitor communications for policy violations (harassment, offensive language, regulatory breaches).

**Insider Risk Use Cases**:
- **Detect Harassment**: Flag emails or chats containing offensive language
- **Regulatory Compliance**: Identify communications that violate financial regulations (e.g., insider trading discussions)
- **Code of Conduct Violations**: Monitor for policy breaches (e.g., sharing confidential information in public channels)

**NexaGlobal Implementation**:
- Configure policies to scan emails, Teams chats, and Yammer posts
- Use **pre-built classifiers** for offensive language, adult content, and threats
- Route flagged communications to compliance reviewers for investigation

---

### User and Entity Behavior Analytics (UEBA)

**Purpose**: Machine learning-based detection of unusual user and entity behaviors.

**Integration**: UEBA is integrated into **Microsoft Defender for Cloud Apps** and **Microsoft Sentinel**.

**Insider Risk Use Cases**:
- **Baseline Deviation**: Detect when user behavior deviates from established norms
- **Peer Group Analysis**: Compare user activity to peers in similar roles
- **Threat Scoring**: Assign risk scores based on multiple behavioral indicators

**NexaGlobal Implementation**:
- Enable UEBA in Microsoft Sentinel
- Configure **anomaly detection rules** for:
  - Unusual data access patterns
  - Atypical login times or locations
  - Mass file downloads or deletions
- Integrate UEBA alerts with Insider Risk Management for unified case management

---

## 4. Data Integration and Holistic View

**Objective**: Ensure Insider Risk Management has access to all relevant data sources for comprehensive risk detection.

**Data Sources to Integrate**:
- **Microsoft 365**: Email, OneDrive, SharePoint, Teams
- **Azure AD**: Sign-in logs, risky sign-ins, conditional access events
- **Endpoints**: File activity, USB usage, application installations (via Defender for Endpoint)
- **Network**: VPN logs, firewall logs, proxy logs (via Microsoft Sentinel)
- **HR Systems**: Employee status changes (resignation, termination, role changes)

**Integration Approach**:
- Use **Microsoft Graph API** to pull data from Microsoft 365 and Azure AD
- Use **HR connectors** to import employee lifecycle events
- Use **Microsoft Sentinel** to aggregate logs from non-Microsoft sources

---

## 5. Privacy and Legal Considerations

### Privacy-First Approach

**Pseudonymization**: User identities are masked until an investigation is warranted, protecting employee privacy.

**Role-Based Access**: Only authorized personnel (security analysts, compliance officers) can view insider risk alerts.

**Audit Trail**: All access to insider risk data is logged for accountability.

### Legal Compliance

**Employee Notification**: Ensure employee handbook and acceptable use policies disclose monitoring practices.

**Data Retention**: Retain insider risk data only as long as necessary for investigations and compliance (typically 1-2 years).

**Regulatory Alignment**: Ensure monitoring practices comply with GDPR (EU), CCPA (California), and other privacy regulations.

---

## Benefits to NexaGlobal Ltd.

| Area | Benefit |
|------|---------|
| **Threat Detection** | Early identification of data theft, policy violations, and compromised accounts |
| **Data Protection** | Prevent exfiltration of intellectual property and customer data |
| **Compliance** | Demonstrate due diligence in protecting sensitive information (ISO 27001, SOC 2) |
| **Incident Response** | Streamlined investigation workflows reduce time to resolution |
| **Employee Privacy** | Privacy-first approach balances security with employee rights |

---

## Tools Summary

- **Microsoft Insider Risk Management**: Behavioral analytics and case management
- **Microsoft Defender for Identity**: Active Directory threat detection
- **Microsoft Purview Information Protection**: Data classification and DLP
- **Azure AD Identity Protection**: Risk-based authentication
- **Microsoft Defender for Cloud Apps**: CASB for cloud app monitoring
- **Office 365 Audit Log**: Comprehensive activity logging
- **Office 365 Communication Compliance**: Policy violation detection in communications
- **User and Entity Behavior Analytics (UEBA)**: Machine learning-based anomaly detection

---

**Next**: [Information Protection →](08-information-protection.md)
