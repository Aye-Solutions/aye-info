# ![Aye Logo](https://aye-ai.org/favicon.ico) Aye — Security & Compliance

![GDPR Compliant](https://img.shields.io/badge/GDPR-Compliant-green?style=flat-square)
![ISO 27001 Ready](https://img.shields.io/badge/ISO_27001-Ready-blue?style=flat-square)
![ISO 27701 Ready](https://img.shields.io/badge/ISO_27701-Ready-blue?style=flat-square)
![Cloud Security](https://img.shields.io/badge/Cloud-Security-blueviolet?style=flat-square)
![AI Governance](https://img.shields.io/badge/AI-Governance-orange?style=flat-square)
![Biometric Security](https://img.shields.io/badge/Biometrics-Secure-lightgrey?style=flat-square)

_Last updated: January 2026_

This document provides a transparent overview of the security architecture, privacy controls, and global compliance posture of **Aye** and its products, including **AyeFace**, a biometric-enabled payment, wallet, and loyalty platform.

Security, privacy, and regulatory compliance are foundational principles in Aye’s product design, technical architecture, and operational governance.

---

## 1. Company & Product Scope

Aye operates a technology platform that enables:

- Biometric-based user authentication (AyeFace)
- Wallet and loyalty orchestration
- Payment initiation through licensed financial institutions
- AI-driven personalization and fraud risk detection

Aye **is not a bank** and **does not directly settle funds**. Payment authorization and settlement are executed by **licensed merchant acquirers and payment service providers** in accordance with applicable financial regulations.

---

## 2. Privacy & Data Protection Framework

### 2.1 Applicable Regulations

Aye aligns its data protection practices with major global privacy frameworks, including:

- EU General Data Protection Regulation (GDPR)
- Malaysia Personal Data Protection Act (PDPA)
- Singapore Personal Data Protection Act (PDPA)

These frameworks govern the collection, processing, storage, transfer, and deletion of personal and biometric data.

### 2.2 Data Protection Principles

Across all systems, Aye applies:

- **Explicit and informed consent**, especially for biometric data
- **Purpose limitation** — data used only for stated functions
- **Data minimisation**
- **Security by design and by default**
- **User rights enablement** (access, correction, deletion where applicable)

### 2.3 Biometric Data Handling

Biometric data is treated as **sensitive personal data**.

- Raw facial images are **not stored**
- Facial data is converted into **non-reversible mathematical templates**
- Templates are encrypted and access-controlled
- Processing occurs only after **explicit user opt-in**

Biometric data is never sold, reused, or shared outside its stated purpose.

---

## 3. AI Governance & Responsible Use

Aye uses AI to support authentication, fraud detection, and personalization.

### 3.1 AI Controls

- Human oversight for critical decision paths
- Continuous monitoring for performance, drift, and anomalies
- Audit logging for AI-driven actions
- Monitoring for bias and false-acceptance rates in biometric systems

### 3.2 Regulatory Readiness

Aye’s AI governance is designed to be compatible with emerging global AI regulations, emphasizing:

- Transparency and traceability
- Explainability where applicable
- Accountability and risk-based controls

---

## 4. Fintech & Payments Compliance

### 4.1 Payment Architecture

- Payments are executed through **licensed banks and acquirers**
- Aye acts as a **technology orchestration layer**
- Aye does not store card numbers or bank credentials

### 4.2 Financial Crime Risk Controls

Aye supports ecosystem-level risk management through:

- Identity verification workflows
- Transaction anomaly detection
- Fraud pattern analysis
- Alignment with FATF AML/CFT best practices

Final AML/KYC responsibility remains with licensed financial institutions.

---

## 5. Infrastructure & Cloud Security

### 5.1 Cloud Environment

Aye operates primarily on **Google Cloud Platform (GCP)** using enterprise-grade security controls, including:

- Zero-trust network principles
- Network segmentation
- Encryption at rest and in transit
- Identity and Access Management (IAM)
- Secure CI/CD pipelines

### 5.2 Google Cloud Security Command Center

Aye uses **Google Cloud Security Command Center (SCC)** as a centralized security management and posture monitoring platform to:

- Detect infrastructure misconfigurations
- Identify vulnerabilities and threats
- Maintain continuous compliance visibility
- Provide real-time security findings and alerts

Security Command Center enables proactive risk detection, prioritization, and remediation across cloud assets.

---

## 6. Cryptographic Standards

Aye applies industry-recognized cryptographic standards, including:

- **AES-256** for data at rest
- **TLS 1.2 / TLS 1.3** for data in transit
- **Public-key cryptography (ECC / RSA)** for authentication and signing
- **Secure hashing (e.g. SHA-256 or stronger)** for integrity verification
- Managed **Key Management Services (KMS)** and hardware-backed protection where available

Cryptographic keys are never hardcoded in application logic.

---

## 7. Blockchain-Based Security Architecture

### 7.1 Purpose of Blockchain Usage

Blockchain is used selectively as a **security and integrity layer**, not as a payment rail.

Primary objectives include:

- Tamper-evident audit trails
- Non-repudiation of critical events
- Cross-party trust without exposing sensitive data

### 7.2 On-Chain vs Off-Chain Data

**On-chain (hashed or encrypted references only):**

- Consent proofs
- Authentication or transaction event hashes
- System integrity checkpoints
- Configuration or model version fingerprints

**Never stored on-chain:**

- Biometric images or templates
- Personal Identifiable Information (PII)
- Payment credentials
- Monetary transaction values

All sensitive data remains **off-chain**, encrypted, and access-controlled.

### 7.3 Biometric Integrity Verification

Blockchain enables verification that:

- Biometric templates have not been altered
- User consent existed at the time of use
- Authentication events are tamper-evident

This enhances auditability without decentralizing personal data.

### 7.4 Smart Contracts (If Applicable)

Smart contracts, where used, are limited to:

- Event verification
- Timestamping
- Integrity validation

They **do not**:

- Authorize payments
- Transfer funds
- Replace regulated financial institutions

---

## 8. Biometric Liveness & Anti-Spoofing

### 8.1 Tencent Liveness Detection

Aye integrates **Tencent liveness detection technology** to mitigate biometric spoofing attacks, including:

- Printed photos
- Screen replays
- Video injections
- Mask-based impersonation

Tencent’s liveness detection provides multi-dimensional facial analysis and real-time verification, significantly reducing false acceptance rates in physical and digital environments.

---

## 9. Information Security Standards Alignment

Aye aligns its internal controls with internationally recognized standards, including:

- **ISO/IEC 27001** — Information Security Management
- **ISO/IEC 27701** — Privacy Information Management
- **ISO/IEC JTC 1/SC 37** — Biometrics standards
- Secure Software Development Lifecycle (SSDLC) practices

Formal certifications may be pursued as the organization scales.

---

## 10. Incident Response & Monitoring

Aye maintains documented incident response procedures covering:

- Detection and containment
- Impact assessment
- Regulatory and stakeholder notification where required
- Root cause analysis and remediation

Security events are monitored continuously across infrastructure and application layers.

---

## 11. User & Merchant Rights

Users and merchants are entitled to:

- Transparency on data usage
- Access and correction of personal data
- Consent withdrawal where legally applicable
- Secure deletion aligned with regulatory requirements

Requests can be submitted through Aye’s official support channels.

---

## 12. Continuous Compliance & Governance

Aye maintains ongoing compliance through:

- Internal risk and security reviews
- Third-party security assessments
- Regulatory horizon scanning
- Employee training on privacy and security

Security and compliance are treated as **continuous processes**, not one-time certifications.

---

## 13. Contact

For security or compliance inquiries, please refer to the contact details listed on Aye’s official privacy and legal pages.
