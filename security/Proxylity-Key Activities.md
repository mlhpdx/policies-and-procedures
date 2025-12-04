### **1. Security / Confidentiality**

| Key Activity                                | Purpose / Rationale                                                            | Evidence / Artifact                                      |
| ------------------------------------------- | ------------------------------------------------------------------------------ | -------------------------------------------------------- |
| **Access Management Reviews**               | Ensure only authorized personnel have access to production systems and secrets | Quarterly IAM reviews, MFA logs                          |
| **Credential & Secret Rotation**            | Limit exposure if credentials are compromised                                  | Secrets rotation logs (Secrets Manager, Parameter Store) |
| **Code Review & Merge Approval**            | Prevent introduction of vulnerabilities in software                            | Pull request approvals, review checklists                |
| **Dependency and Vulnerability Management** | Detect and patch vulnerable libraries                                          | CVE scans, dependency reports                            |
| **Encryption in Transit & At Rest**         | Protect configuration data and internal communications                         | TLS certificates, KMS usage logs                         |
| **Logging & Monitoring**                    | Detect unauthorized access or anomalous activity                               | CloudWatch, VPC flow logs, alert reports                 |

---

### **2. Availability / Continuity**

| Key Activity                        | Purpose / Rationale                                  | Evidence / Artifact                                |
| ----------------------------------- | ---------------------------------------------------- | -------------------------------------------------- |
| **Multi-region Deployment Testing** | Validate resilience to AWS region outages            | Deployment runbooks, test results                  |
| **Backup & Restore Validation**     | Ensure internal configuration/state can be recovered | Backup logs, restore test documentation            |
| **CI/CD Pipeline Health Checks**    | Maintain deployment reliability                      | CodeBuild/CodeDeploy build logs                    |
| **Incident Response Testing**       | Ensure rapid response to service-impacting events    | Tabletop exercise notes, incident response reports |

---

### **3. Processing Integrity**

| Key Activity                      | Purpose / Rationale                                             | Evidence / Artifact            |
| --------------------------------- | --------------------------------------------------------------- | ------------------------------ |
| **Automated Deployment Checks**   | Prevent misconfiguration or downtime                            | Pipeline logs, automated tests |
| **Configuration Management**      | Ensure only validated, approved configurations reach production | Git history, review approvals  |
| **Monitoring of Service Metrics** | Detect degraded service performance                             | CloudWatch metrics, alerts     |

---

### **4. Vendor / Third-Party Risk**

| Key Activity                          | Purpose / Rationale                                   | Evidence / Artifact               |
| ------------------------------------- | ----------------------------------------------------- | --------------------------------- |
| **AWS Service Dependency Monitoring** | Ensure uptime and incident response coordination      | AWS Health Dashboard, SLA reports |
| **Vendor Access Reviews**             | Ensure third-party accounts are limited and monitored | Vendor IAM logs, access approvals |

---

### **5. Employee Awareness & Training**

| Key Activity                    | Purpose / Rationale                                | Evidence / Artifact                         |
| ------------------------------- | -------------------------------------------------- | ------------------------------------------- |
| **Security Awareness Training** | Reduce risk of human error                         | Training attendance, acknowledgment forms   |
| **Policy Acknowledgment**       | Ensure personnel understand their responsibilities | Signed security policy acknowledgment forms |

---

#### **Summary**

For Proxylity, **key activities are largely operational controls**:

* Focused on **configuration confidentiality, platform integrity, and availability**.
* Auditable through **CI/CD logs, IAM reviews, cloud monitoring, and backup validation**.
* Designed for **low-overhead, fully remote operations** but sufficient for SOC-2 alignment.

