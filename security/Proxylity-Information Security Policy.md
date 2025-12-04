# **Proxylity LLC — Information Security Policy**
**Version:** 1.0  
**Approved By:** Executive Management  
**Last Updated:** 2025-12-04  

---

## **1. Purpose**
The purpose of this policy is to define Proxylity LLC’s approach to information security; to protect the confidentiality, integrity, and availability of corporate and customer data; and to support business continuity, risk management, and regulatory compliance.

---

## **2. Scope**
This policy applies to:

- All Proxylity employees, contractors, and temporary workers.
- All systems, cloud infrastructure, source code, deployment pipelines, and configuration data owned or managed by Proxylity.
- All third-party services used as part of business operations or customer delivery.

Proxylity does **not store customer PII**, nor persist customer-generated packet content passing through the UDP Gateway platform. Customer configuration data is collected only to enable service delivery and is treated as **confidential**.

---

## **3. Information Classification**
Proxylity classifies information into three categories:

| Classification | Description | Handling |
|---------------|-------------|----------|
| **Public** | Approved for public distribution | No restrictions |
| **Internal** | General operations, non-public corporate information | Internal access only |
| **Confidential** | Platform configuration data, credentials, operational security, architecture details | Limited to authorized personnel only; encrypted in transit and at rest |

Proxylity **does not store customer PII** and **does not retain customer traffic data**.

---

## **4. Access Control**
- Access is granted on the principle of **Least Privilege**.
- All systems require **strong authentication**; MFA is mandatory where supported.
- Access revocation occurs immediately upon role change or termination.
- Administrative access must use secure protocols and dedicated privileged accounts.

---

## **5. Cloud Security**
Proxylity operates exclusively in AWS and relies on AWS-native security capabilities:

- Network segregation through VPC isolation.
- Encryption in transit via TLS 1.2+.
- Encryption at rest using KMS-managed keys.
- IAM role-based permissions for all systems and automation.
- Logging and monitoring of cloud activities where applicable.

**No customer packet data is stored** within Proxylity systems.

---

## **6. Software Development Security**
- CI/CD pipelines enforce controlled deployments and peer-reviewed merges.
- Secrets are managed through secure mechanisms (AWS Secrets Manager / Parameter Store).
- Third-party code or dependencies are evaluated for licensing and security risk.
- No customer data is used in development environments.

---

## **7. Incident Response**
Proxylity maintains an Incident Response Plan that includes:

- Detection and classification of security events.
- Containment, eradication, and recovery procedures.
- Notification to affected parties where required by law or contract.
- Post-incident corrective action and documentation.

---

## **8. Data Retention and Deletion**

Proxylity implements a comprehensive data retention and deletion policy to minimize security exposure and ensure compliance with legal and regulatory obligations.

**Retention Periods:**
- **Customer Configuration Data:** Retained until account termination, then permanently deleted
- **Configuration Change Audit Logs:** Retained for three (3) years
- **System Operation Logs:** Retained for eighty-nine (89) days
- **Backup Data:** Deleted according to the same timeline as live data
- **CloudTrail Logs:** Retained indefinitely (AWS default for compliance)

**Deletion Procedures:**
- All deletions are performed using AWS-native mechanisms
- Cross-region replication copies are deleted simultaneously (us-west-2, us-east-1, eu-west-1)
- Deletion is logged and verified through CloudTrail
- Data subject requests are processed within thirty (30) days
- Legal hold procedures are in place for litigation or government investigations

For detailed procedures, see **Proxylity LLC — Data Retention and Deletion Policy**.

---

## **9. Vendor and Third-Party Risk**
- Vendors must support industry-standard security practices.
- Access to Proxylity systems is monitored and restricted.
- AWS Marketplace serves as the merchant of record for billing activities.

---

## **10. Business Continuity & Resilience**
- Proxylity's platform is designed for multi-region operation.
- Systems can withstand a regional outage without service loss.
- Regular backups exist for internal corporate systems; no customer packet data is backed up.

---

## **11. Compliance**
Proxylity intends to pursue independent compliance attestations (e.g., SOC 2).  
Regulations regarding PII (GDPR, CCPA) currently **do not apply** as Proxylity does **not store or process personal data**.

All compliance requirements mandated by contract or law will be followed.

---

## **13. Policy Review**
This policy is reviewed at least annually and upon significant change in:

- Business operations
- Regulatory obligation
- Platform architecture or risk profile

---

## **14. Employee Responsibility**
All personnel must:

- Understand and follow this policy.
- Complete required security training.
- Report suspected security incidents immediately.

Failure to comply may result in disciplinary action up to termination.

---

**Approved By:** Lee Harding
**Date:** 2025-12-04

