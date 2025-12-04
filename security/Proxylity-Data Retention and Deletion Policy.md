# **Proxylity LLC — Data Retention and Deletion Policy**

**Version:** 1.0  
**Approved By:** Lee Harding
**Last Updated:** 2025-12-04
**Classification:** Confidential — Internal Use Only

---

## **1. Purpose**

This policy defines data retention and deletion procedures for Proxylity LLC to ensure:

- Compliance with legal, regulatory, and contractual obligations
- Appropriate data lifecycle management
- Minimization of security and privacy exposure from unnecessary data retention
- Clear procedures for secure data destruction

---

## **2. Scope**

This policy applies to:

- All customer configuration data stored in production systems
- System operation logs and monitoring data
- Customer activity and audit logs
- Internal corporate data and backups
- Data residing in AWS S3, DynamoDB, and other cloud storage services

---

## **3. Data Classification and Retention Periods**

Proxylity retains data according to the following classifications:

### **3.1 Customer Configuration Data**

| Data Type | Description | Retention Period | Justification |
|-----------|-------------|-----------------|---------------|
| Customer Configuration | Service settings, allowed IPs, ARN mappings | Until account termination + 0 days | Required for service delivery; no longer needed upon termination |
| Audit Logs (Configuration Changes) | Log of customer-initiated configuration changes | 3 years | Required for compliance, security investigation, and audit trails |

**Retention End:** Customer configuration data is **permanently deleted upon account termination**. Audit logs of configuration changes are retained for **three (3) years** from the date of last activity.

---

### **3.2 System Operation and Monitoring Data**

| Data Type | Description | Retention Period | Justification |
|-----------|-------------|-----------------|---------------|
| CloudWatch Logs | System performance, errors, API calls | 89 days | Sufficient for operational troubleshooting and incident investigation |
| VPC Flow Logs | Network traffic metadata | 89 days | Required for network security monitoring and anomaly detection |
| Application Logs | Error traces, deployment logs, system events | 89 days | Required for debugging, performance analysis, and incident response |
| CloudTrail Logs | AWS API calls and account activity | Indefinite (AWS default) | Required by AWS for security compliance and audit |

---

### **3.3 Backup Data**

| Data Type | Description | Retention Period | Justification |
|-----------|-----------|-----------------|---------------|
| Customer Configuration Backups | Replicated configuration data across AWS regions | Matches live data retention (0 days post-termination) | Required for business continuity; deleted with customer data |
| Internal System Backups | Backups of internal tools and corporate systems | 30 days (rolling) | Sufficient for operational recovery; not required indefinitely |

---

### **3.4 Employee and HR Data**

| Data Type | Description | Retention Period | Justification |
|-----------|-----------|-----------------|---------------|
| Employment Records | Offer letters, agreements, performance reviews | Duration of employment + 3 years | Required by labor law and tax obligations |
| Background Check Records | Pre-employment screening documentation | Duration of employment + 3 years | Required for compliance and dispute resolution |
| Access Control Logs | MFA logs, system access records | 1 year | Required for security audits and incident investigation |

---

## **4. Data Deletion Procedures**

### **4.1 Customer Data Deletion Upon Account Termination**

When a customer's account is terminated (either by the customer or by Proxylity):

1. **Notification:** Customer is notified of the termination and provided a notice period (typically 30 days) to retrieve their configuration data if needed.

2. **Data Preservation:** Customer configuration data remains accessible during the notice period.

3. **Final Deletion:** Upon expiration of the notice period or explicit customer request:
   - All customer configuration data is permanently deleted from primary data stores (DynamoDB)
   - All replicated copies across AWS regions (us-west-2, us-east-1, eu-west-1) are deleted
   - Deletion is performed using AWS-native deletion mechanisms (DynamoDB DeleteItem)
   - Verification: Confirmed deletion is logged in internal audit records

4. **Audit Log Retention:** Logs of customer configuration changes remain in CloudWatch for three (3) years to support compliance and security investigations.

### **4.2 System Log Deletion**

System operation logs (CloudWatch, VPC Flow Logs, Application Logs) are automatically deleted according to retention periods:

- **Process:** AWS CloudWatch log groups are configured with automatic log expiration (89 days)
- **Verification:** Automatic expiration is monitored and logged
- **Exception:** Logs related to security incidents are retained beyond normal retention periods until incident investigation is complete and approved for deletion

### **4.3 Backup Data Deletion**

- **Timing:** Backup data is deleted according to the same timeline as live data
- **Cross-Region Replication:** All replicated copies in all AWS regions (us-west-2, us-east-1, eu-west-1) are deleted simultaneously
- **Verification:** Deletion is confirmed through AWS API calls and logged in CloudTrail

### **4.4 Long-Term Data Deletion**

For data retained beyond 1 year (e.g., audit logs retained for 3 years):

- **Scheduling:** Deletion is scheduled in advance and tracked in internal systems
- **Approval:** Deletion of audit logs or compliance-related data requires approval from executive management
- **Verification:** Deletion is documented with timestamp and verification details
- **Retention of Deletion Records:** Records of deletion (timestamp, data type, quantity) are maintained for audit purposes

---

## **5. Data Subject Requests**

Proxylity does not store personally identifiable information (PII) about individuals. However, if a customer requests deletion or access to their data:

1. **Access Requests:** Customers may request access to their configuration data through normal support channels.

2. **Deletion Requests:** Customers may request early deletion of their data by submitting a formal deletion request to support@proxylity.io.

3. **Processing:** Deletion requests are processed within 30 days of receipt.

---

## **6. Legal Hold and Exception Procedures**

If litigation, government investigation, or other legal proceeding requires data retention beyond normal periods:

1. **Notification:** Legal team notifies system administrators of the legal hold requirement
2. **Suspension:** Automatic deletion is suspended for affected data
3. **Segregation:** Data subject to legal hold is flagged and isolated from normal deletion schedules
4. **Documentation:** Legal hold is documented with case reference and expected duration
5. **Release:** Upon legal case closure, data is deleted according to normal procedures

---

## **7. Responsibility and Accountability**

| Role | Responsibility |
|------|-----------------|
| **Engineering/DevOps** | Implement and execute data deletion procedures; maintain deletion logs |
| **Compliance Officer** | Oversee data retention compliance; audit deletion procedures |
| **Executive Management** | Approve exceptions and long-term deletions; review retention policy annually |

---

## **8. Monitoring and Auditing**

- **Monthly Review:** Engineering reviews deletion logs and confirms successful data removal
- **Quarterly Audit:** Compliance team audits data retention compliance against this policy
- **Annual Review:** Full review of data retention periods and procedures; policy updates as needed

---

## **9. Policy Review**

This policy is reviewed at least **annually** and upon:

- Significant changes to system architecture or data storage
- Introduction of new data types or customer data usage
- Changes to legal, regulatory, or contractual obligations
- After any data deletion issue or incident

---

## **10. Exceptions and Deviations**

Any deviation from this policy (e.g., extended retention for specific data) must be:

1. Documented with business justification
2. Approved by Executive Management
3. Time-limited with a sunset date
4. Reviewed in accordance with Section 8 above

---

**Approved By:** Lee Harding  
**Date:** 2025-12-04
