# AyeFace Security & Compliance

**Last reviewed:** 27 October 2026 · **Maintained by:** Aye Engineering · **Review cadence:** quarterly

This document sets out how Aye Global Holdings Pte. Ltd. ("Aye") protects people, merchants and data across
**AyeFace**, our consent-based identity, loyalty and payments platform. It complements the
[Security & Compliance](https://aye-ai.org/security) page and the [Privacy Policy](https://aye-ai.org/privacy),
which are the authoritative statements of our commitments. For how the platform is built, see
[ARCHITECTURE.md](ARCHITECTURE.md).

---

## At a glance

| Area | Our position |
|---|---|
| **Biometrics** | Opt-in, consent-based and withdrawable · certified liveness on every scan · no face images kept by AyeFace · encrypted templates that cannot be turned back into a face |
| **Privacy** | Aligned with GDPR and data-protection laws across Southeast Asia · data minimisation · user rights to access, correction and deletion |
| **Payments** | Settled by licensed acquirers and schemes · tokenised credentials, no card numbers stored · strong customer authentication |
| **Cloud** | Google Cloud in the Asia-Pacific region · posture monitoring in Security Command Center · least-privilege access |
| **Cryptography** | TLS 1.3 in transit · AES-256 at rest · signing keys in Google Cloud KMS |
| **Assurance** | Liveness tested to ISO/IEC 30107-3 · SOC 2-aligned controls, certification in progress · PCI-DSS-certified payment partners |

---

## 1. Scope

AyeFace lets a person who chooses to enrol be recognised at a participating checkout, have their loyalty
rewards applied, and pay with the method they choose, in one interaction. Aye is a technology provider. **Aye is
not a bank and does not hold merchant funds.** Payment authorisation and settlement are carried out by licensed
acquirers and payment schemes under their own regulation.

---

## 2. Biometric data

Biometric data is treated as sensitive personal data throughout.

- **Consent first.** Enrolment is opt-in. Consent is the lawful basis for all biometric processing and can be
  withdrawn at any time from the user portal. Every terminal also accepts cards, QR and wallets, so nobody has to
  scan to pay.
- **Certified liveness.** Every scan passes a certified liveness check, tested to ISO/IEC 30107-3, which confirms
  a real person is present and resists printed photos, screen replays and masks.
- **No face images kept.** The captured image is sent encrypted to the AyeFace recognition engine, operated with
  a certified enterprise partner in the Asia-Pacific region, which creates or matches the person's template. The
  image is deleted within 10 minutes. AyeFace's own systems store a reference to the template, not the image.
- **Irreversible, encrypted templates.** Templates are encrypted at rest and cannot be turned back into a face.
- **Careful matching.** Checkout does not guess between close candidates; an ambiguous match requires an extra
  verification step before anything is paid.
- **Merchants receive no biometric data.** Merchants see store activity and the customer's chosen payment
  options, not images or templates.
- **Purpose limitation.** Biometric data is used to recognise and authenticate the person and to improve the
  accuracy and security of recognition and liveness, as described in the Privacy Policy. It is not used for
  marketing or personalisation and is not sold.
- **Deletion that reaches the engine.** Withdrawing consent or closing an account removes the template from the
  recognition group as well as from AyeFace's own records, within 30 days.

---

## 3. Privacy and data protection

AyeFace is designed to align with the data-protection laws of the markets we serve, including:

- EU General Data Protection Regulation (GDPR)
- Malaysia Personal Data Protection Act 2010
- Singapore Personal Data Protection Act 2012
- Philippines Data Privacy Act of 2012
- Thailand Personal Data Protection Act B.E. 2562
- Vietnam Personal Data Protection Decree 13/2023/ND-CP
- Indonesia Personal Data Protection Law No. 27/2022
- Brunei Personal Data Protection Order 2021

Across all of them we apply explicit consent for biometric data, purpose limitation, data minimisation, security
by design and by default, and practical support for access, correction, deletion and consent withdrawal.
Retention periods and cross-border transfers are set out in the [Privacy Policy](https://aye-ai.org/privacy).

Data from child and teen accounts is used only to operate the account and process transactions, with any
improvement use subject to separate parental opt-in, as described in the Privacy Policy.

---

## 4. Payments security

- **Licensed rails.** Charges are routed to licensed acquirers or national QR schemes. Settlement remains with
  the acquirer.
- **Tokenisation.** Card details are captured on processors' hosted surfaces. We store provider tokens and
  non-sensitive display data (brand, last four digits, expiry), not card numbers. Card processing is handled by
  PCI-DSS-certified partners.
- **Strong customer authentication.** When an issuer asks to re-authenticate a stored card, the bank challenge is
  presented in the app or browser, and the outcome is confirmed through an idempotent verify path.
- **Verified webhooks.** Provider webhooks are signature-verified, logged and reconciled against orders.
- **A scan alone pays nothing.** Every payment needs a fresh live scan, and funds settle only to verified,
  registered merchants.

---

## 5. Cloud and infrastructure

- **Google Cloud** in the Asia-Pacific region, on Kubernetes (GKE), with services deployed through GitOps so every
  environment is declared in the repository.
- **Separate environments** for development and production.
- **Least-privilege access** through Identity and Access Management, with role-based access to production.
- **Posture monitoring.** Google Cloud Security Command Center is used to detect misconfigurations,
  vulnerabilities and threats, with findings reviewed and remediated.
- **Resilience.** A 99.9% platform uptime target, excluding third-party bank and payment networks.

---

## 6. Cryptography

- **TLS 1.3** for data in transit.
- **AES-256** for data at rest.
- **Google Cloud KMS** for signing keys.
- Secrets are kept out of source code.

---

## 7. Secure development

- **Continuous integration** with GitHub Actions on every change.
- **SonarQube quality gates** and **Dependabot** for dependency and base-image updates.
- **Contract tests.** Every payment gateway must pass the same shared contract test suite.
- **Decisions of record.** Significant design choices are written down as Architecture Decision Records.
- **Minimal containers.** Multi-stage images, with the newest services running as non-root.

---

## 8. AI governance

- **Review before effect.** AI suggests; merchants review changes before they go live.
- **Biometric separation.** Personalisation uses transaction and preference data, not biometric templates.
- **Agent access is scoped.** AI assistants and AI Agents reach AyeFace through the partner API and MCP under
  scoped, revocable permissions.

---

## 9. Logging, monitoring and incident response

- **Error tracking** with Sentry and **structured logging** with sensitive fields redacted. Logs do not contain
  face images.
- **Documented incident response** covering detection and containment, impact assessment, notification to
  regulators and affected people where the law requires it, and root-cause remediation.
- **Regular penetration testing** and vulnerability assessments.

---

## 10. Under development: blockchain integrity layer

We are developing a blockchain-anchored integrity layer, so that critical events can be shown to be unaltered
and verified independently. It is not in production yet.

- **What it records:** hashed or encrypted references only, such as consent proofs, authentication and
  transaction event hashes, and configuration or model-version fingerprints.
- **What stays off-chain:** biometric images and templates, personal data, payment credentials and transaction
  values. These remain encrypted and access-controlled in our own systems.
- **What it is not:** a payment rail. It does not authorise payments, transfer funds or replace regulated
  financial institutions.

---

## 11. Standards

| Standard | Status |
|---|---|
| ISO/IEC 30107-3 (presentation attack detection) | Liveness tested to the standard |
| SOC 2 Trust Service Criteria | Controls aligned; certification in progress |
| ISO/IEC 27001 and ISO/IEC 27701 | Controls aligned |
| PCI-DSS | Card processing by certified partners; no card numbers stored by AyeFace |

---

## 12. Reporting a vulnerability

If you believe you have found a security vulnerability, email **security@aye-ai.org**. We take every report
seriously and aim to respond within 24 hours. Please give us reasonable time to fix an issue before disclosing
it, and do not access or modify data that is not yours.

---

## 13. Contact

- Privacy and data requests: **privacy@aye-ai.org**
- Security: **security@aye-ai.org**
- Everything else: [aye-ai.org/contact](https://aye-ai.org/contact) · [Telegram](https://t.me/paywithayeface)
