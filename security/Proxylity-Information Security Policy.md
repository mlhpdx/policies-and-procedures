# **Proxylity LLC — Information Security Policy**
**Version:** 1.0  
**Approved By:** Lee Harding  
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

Proxylity implements access controls to ensure only authorized personnel can access systems and data.

**Principles:**
- Access is granted on the principle of **Least Privilege**
- All access requires business justification and appropriate approval
- Access is role-based, with permissions aligned to job responsibilities

**Authentication:**
- All systems require **strong authentication**
- Multi-factor authentication (MFA) is mandatory for all accounts where supported
- MFA is required for AWS console access, GitHub, and administrative tools
- Service accounts use IAM roles with least-privilege permissions

**Access Reviews:**
- IAM permissions and access rights are reviewed quarterly
- Access logs (MFA, login attempts) are retained and available for audit
- Unused accounts and permissions are identified and removed

**Access Revocation:**
- Access is revoked immediately upon role change or termination
- Process includes revocation of AWS IAM, GitHub, and all corporate systems
- Return of company assets is verified upon termination

**Privileged Access:**
- Administrative access requires dedicated privileged accounts
- Privileged access uses secure protocols and is logged
- Root account access is restricted and protected with MFA

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

Proxylity maintains secure software development practices to protect platform integrity and prevent vulnerabilities.

**Infrastructure as Code:**
- All infrastructure and system configurations are maintained as Infrastructure as Code (IaC) in CloudFormation templates
- Configuration changes are version-controlled in Git with full history
- Changes require review and approval before merge

**Change Management:**
- CI/CD pipelines enforce controlled deployments
- All code changes require review before merging
- Deployment scripts in each repository enable local deployment capability if CI/CD is unavailable
- Configuration changes are logged and retained for three years

**Security Configuration:**
- Security configurations are automatically evaluated via AWS Config and Security Hub
- Manual security inspections and reviews are performed at least quarterly
- Security and hardening standards are maintained and documented

**Secrets Management:**
- Secrets are managed through AWS Secrets Manager and Parameter Store
- No secrets are stored in source code repositories
- Credentials and secrets are rotated according to defined schedules

**Dependency Management:**
- Third-party code and dependencies are evaluated for licensing and security risk
- Dependencies are updated frequently (more often than monthly)
- CVE scans and dependency vulnerability reports are reviewed regularly

**Development Environment:**
- No customer data is used in development environments
- Development and production environments are logically separated

---

## **7. Incident Response**

Proxylity maintains a formal Incident Response Plan to detect, respond to, and recover from security incidents.

**Incident Lifecycle:**
- Detection and identification through monitoring, alerts, and staff reporting
- Classification and prioritization (Low, Medium, High, Critical)
- Containment, eradication, and recovery procedures
- Post-incident review and corrective action

**Monitoring and Detection:**
- CloudWatch monitoring and alerting for system health and anomalies
- Log monitoring for unusual or suspicious activities
- Comprehensive logging enabled to support incident investigation
- Logs retained for sufficient time to investigate incidents (89 days minimum)

**Notification:**
- Internal escalation to executive team for critical incidents
- Customer notification within 48 hours after vulnerability is resolved (unless customer engagement is required for remediation)
- Affected parties notified where required by law or contract
- Customers may report security incidents via documented disclosure process on public website
- Service status and security bulletins published at https://status.proxylity.com

**Incident Resources:**
- Relevant logs and incident reports available to affected customers within scope of their use
- Disaster recovery plans documented for worst-case scenarios

**Training and Testing:**
- All employees complete annual security awareness and incident response training
- Tabletop exercises performed annually or after significant system changes

For detailed procedures, see **Proxylity LLC — Incident Response Plan**.

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

Proxylity manages third-party vendor relationships to ensure they do not compromise security, availability, or integrity of customer data.

- Vendors are assessed for security practices prior to use and periodically thereafter.
- No third-party vendors have access to customer data (other than AWS as infrastructure provider).
- Access to Proxylity systems by vendors is monitored and restricted to the minimum necessary.
- Critical dependencies (AWS, GitHub) are identified with documented risk mitigations.
- AWS Marketplace serves as merchant of record for billing activities, transferring payment processing risk.
- Vendors with customer data access must notify Proxylity within 24 hours of any security incident.

For detailed vendor assessment procedures and current vendor inventory, see **Proxylity LLC — Vendor and Third-Party Risk Management Policy**.

---

## **10. Business Continuity & Resilience**

Proxylity maintains business continuity capabilities to ensure service availability and rapid recovery from disruptions.

**Platform Resilience:**
- Multi-region deployment across three AWS regions (us-west-2, us-east-1, eu-west-1)
- Architecture designed to tolerate single-region failure without service interruption
- Customer workload distributed across availability zones within each region
- Automated failover capabilities with continuous testing through deployment processes

**Recovery Objectives:**
- **Recovery Time Objective (RTO):** 2 hours for full system rebuild in worst-case scenario
- **Recovery Point Objective (RPO):** 0 hours (no data loss) for customer configuration data
- **Availability Target:** 99.9% uptime (≤44 minutes downtime per month)

**Backup and Recovery:**
- Customer configuration data replicated across three AWS regions
- DynamoDB point-in-time recovery enabled
- Internal corporate systems backed up with 30-day retention
- Recovery procedures documented and tested at least quarterly

**Continuity Testing:**
- Failover exercised continuously through automated deployment processes
- Forced failover testing performed approximately monthly for specific scenarios
- Loss of access and system recovery testing performed at least quarterly

For detailed impact analysis and recovery priorities, see **Proxylity LLC — Business Impact Assessment**.

---

## **11. Compliance**
Proxylity intends to pursue independent compliance attestations (e.g., SOC 2).  

Proxylity minimizes collection of personal data. Customer contact information voluntarily provided for support purposes is handled in accordance with applicable privacy regulations (GDPR, CCPA). Customer configuration data does not include personal data.

All compliance requirements mandated by contract or law will be followed.

---

## **12. Policy Review**
This policy is reviewed at least annually and upon significant change in:

- Business operations
- Regulatory obligation
- Platform architecture or risk profile

---

## **13. Employee Responsibility**
All personnel must:

- Understand and follow this policy.
- Complete required security training.
- Report suspected security incidents immediately.

Failure to comply may result in disciplinary action up to termination.

---

**Approved By:** Lee Harding
**Date:** 2025-12-04

