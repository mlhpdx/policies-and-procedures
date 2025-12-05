# **Proxylity LLC — Vendor and Third-Party Risk Management Policy**

**Version:** 1.0  
**Approved By:** Lee Harding  
**Last Updated:** 2025-12-05  
**Classification:** Confidential — Internal Use Only

---

## **1. Purpose**

This policy defines Proxylity LLC's approach to identifying, assessing, and managing risks associated with third-party vendors, service providers, and business partners. The policy ensures that vendor relationships do not compromise the security, availability, or integrity of Proxylity's platform or customer data.

---

## **2. Scope**

This policy applies to:

- All third-party vendors, service providers, and contractors
- Cloud infrastructure providers (AWS)
- Software development tools and platforms (GitHub)
- Any external party with access to Proxylity systems, data, or operations
- Future vendor relationships as Proxylity grows

**Exclusions:** This policy does not apply to customers or end users of Proxylity services.

---

## **3. Definitions**

| Term | Definition |
|------|------------|
| **Vendor** | Any third party that provides goods, services, or access to systems used by Proxylity |
| **Critical Vendor** | A vendor whose failure or unavailability would significantly impact Proxylity's ability to deliver services |
| **Sub-processor** | A vendor that processes customer data on behalf of Proxylity |
| **Vendor Risk Assessment** | A structured evaluation of a vendor's security practices, reliability, and business stability |

---

## **4. Roles and Responsibilities**

| Role | Responsibility |
|------|-----------------|
| **Vendor Risk Owner** | Identifies vendors requiring assessment; conducts initial and periodic risk assessments; recommends approval or rejection |
| **Vendor Risk Approver** | Approves new vendor relationships; approves risk acceptances for vendor-related risks; authorizes exceptions |
| **Vendor Relationship Manager** | Manages ongoing vendor relationship; monitors vendor performance; escalates issues |

**Current Staffing:** During the startup phase, all roles are held by Lee Harding (Founder/CEO). As the organization grows, these roles will be distributed to appropriate team members.

---

## **5. Vendor Classification**

Vendors are classified based on their criticality and data access:

### **5.1 Criticality Levels**

| Level | Definition | Examples | Assessment Frequency |
|-------|-----------|----------|---------------------|
| **Critical** | Vendor failure would cause service outage or significant business disruption | AWS (infrastructure), GitHub (development) | Annually + upon significant changes |
| **Important** | Vendor failure would cause operational disruption but service could continue | Email providers, monitoring tools | Annually |
| **Standard** | Vendor failure would cause inconvenience but minimal business impact | Office software, documentation tools | Upon onboarding; every 2 years |

### **5.2 Data Access Levels**

| Level | Definition | Examples | Additional Requirements |
|-------|-----------|----------|------------------------|
| **Customer Data Access** | Vendor has access to customer configuration data or could access customer traffic | AWS (infrastructure provider) | Enhanced assessment; contractual data protection requirements |
| **Internal Data Access** | Vendor has access to Proxylity internal systems or data | GitHub (source code), accounting software | Standard assessment; confidentiality requirements |
| **No Data Access** | Vendor provides services without access to Proxylity data | Hardware suppliers, general contractors | Basic assessment |

---

## **6. Current Vendor Inventory**

Proxylity maintains a vendor inventory documenting all third-party relationships:

| Vendor | Service | Criticality | Data Access | Last Assessed | Next Review |
|--------|---------|------------|-------------|---------------|-------------|
| **Amazon Web Services (AWS)** | Cloud infrastructure (compute, storage, networking, database) | Critical | Customer Data Access | 2025-12-05 | 2026-12-05 |
| **GitHub** | Source code repository, CI/CD integration | Critical | Internal Data Access | 2025-12-05 | 2026-12-05 |
| **AWS Marketplace** | Billing and subscription management | Important | No Data Access (merchant of record) | 2025-12-05 | 2026-12-05 |

**Note:** This inventory is updated whenever vendors are added, removed, or change in scope.

---

## **7. Vendor Assessment Process**

### **7.1 New Vendor Assessment**

Before engaging a new vendor:

1. **Identify Need:** Document business need and alternatives considered
2. **Classify Vendor:** Determine criticality level and data access level
3. **Conduct Assessment:** Evaluate vendor using appropriate assessment criteria (Section 8)
4. **Document Findings:** Record assessment results and any identified risks
5. **Approve or Reject:** Vendor Risk Approver reviews and decides
6. **Onboard:** If approved, establish relationship with appropriate controls
7. **Add to Inventory:** Update vendor inventory with new vendor details

### **7.2 Periodic Vendor Review**

Existing vendors are reviewed according to their criticality:

- **Critical Vendors:** Annually and upon significant changes
- **Important Vendors:** Annually
- **Standard Vendors:** Every 2 years

Periodic reviews include:
- Verification of continued business need
- Review of vendor security posture and any incidents
- Assessment of vendor performance and reliability
- Update to risk assessment as needed

### **7.3 Triggered Assessments**

Additional assessments are conducted when:

- Vendor experiences a security incident or data breach
- Vendor changes ownership or undergoes significant organizational change
- Vendor's services or scope changes significantly
- Industry reports or news indicate concerns about vendor
- Contract renewal is approaching

---

## **8. Vendor Assessment Criteria**

### **8.1 Security Practices**

| Criterion | Assessment Questions |
|----------|---------------------|
| **Access Control** | Does the vendor implement strong authentication? Is MFA required? How is access managed and revoked? |
| **Encryption** | Is data encrypted in transit and at rest? What encryption standards are used? |
| **Incident Response** | Does the vendor have an incident response plan? How quickly will they notify us of incidents? |
| **Compliance** | Does the vendor hold relevant certifications (SOC 2, ISO 27001)? Are they audited? |
| **Vulnerability Management** | How does the vendor manage vulnerabilities and patching? |

### **8.2 Business Stability**

| Criterion | Assessment Questions |
|----------|---------------------|
| **Financial Health** | Is the vendor financially stable? Any concerns about viability? |
| **Business Continuity** | Does the vendor have business continuity and disaster recovery plans? |
| **Service Level** | What SLAs does the vendor offer? What is their historical uptime? |
| **Support** | What support channels are available? What are response times? |

### **8.3 Contractual Protections**

| Criterion | Assessment Questions |
|----------|---------------------|
| **Data Protection** | Are there contractual requirements for data handling and protection? |
| **Liability** | What liability does the vendor accept for failures or breaches? |
| **Termination** | What are the termination terms? Can we retrieve our data? |
| **Audit Rights** | Do we have the right to audit the vendor's security practices? |

---

## **9. Critical Vendor Risk Mitigations**

### **9.1 Amazon Web Services (AWS)**

**Risk:** AWS is a single point of failure for all infrastructure; AWS account compromise would be catastrophic.

**Mitigations:**
- Multi-region deployment across us-west-2, us-east-1, eu-west-1
- Architecture designed to tolerate single-region failure
- AWS account secured with MFA on root and all IAM users
- Least-privilege IAM policies for all services and users
- AWS Health Dashboard monitoring for service issues
- Reliance on AWS SOC 2, ISO 27001, and other certifications
- AWS shared responsibility model understood and documented

**Residual Risk:** Accepted. AWS is industry-leading infrastructure; alternatives would not materially reduce risk and would significantly increase operational complexity.

### **9.2 GitHub**

**Risk:** GitHub unavailability would block software development and deployment; GitHub compromise could expose source code.

**Mitigations:**
- Repository mirrors maintained in separate location
- Tested cut-over plan for source control recovery if GitHub becomes unavailable
- MFA required for all GitHub accounts
- Branch protection rules enforced
- Dependabot alerts enabled for vulnerability detection
- No secrets stored in repositories

**Residual Risk:** Accepted. GitHub is industry-leading for source control; mitigations reduce impact of unavailability to acceptable levels.

### **9.3 AWS Marketplace**

**Risk:** AWS Marketplace unavailability would block new customer acquisitions; issues could impact billing.

**Mitigations:**
- AWS Marketplace serves as merchant of record, transferring payment processing risk
- No customer payment data stored by Proxylity
- Existing customers continue to operate during Marketplace outages
- AWS Marketplace SLA provides availability commitments

**Residual Risk:** Accepted. Impact limited to new sales; operational service continues.

---

## **10. Vendor Data Protection Requirements**

### **10.1 Customer Data Access**

Vendors with access to customer data must:

- Maintain security practices equivalent to or exceeding Proxylity's standards
- Encrypt data in transit and at rest
- Implement access controls limiting data access to authorized personnel
- Notify Proxylity promptly (within 24 hours) of any security incident affecting our data
- Not share data with sub-processors without Proxylity's written consent
- Delete or return data upon termination of the relationship

**Current Status:** Only AWS has access to customer configuration data. AWS meets all requirements through their published security practices, certifications, and shared responsibility model.

### **10.2 Internal Data Access**

Vendors with access to internal data (e.g., source code) must:

- Maintain reasonable security practices
- Implement access controls
- Notify Proxylity of security incidents affecting our data

### **10.3 No Data Access**

Vendors without data access have no specific data protection requirements beyond standard business practices.

---

## **11. Vendor Incident Response**

### **11.1 Vendor Incident Notification**

If a vendor experiences a security incident:

1. **Receive Notification:** Vendor notifies Proxylity of incident
2. **Assess Impact:** Determine if Proxylity data or services are affected
3. **Activate IRP:** If customer data or services are impacted, activate Proxylity Incident Response Plan
4. **Document:** Record incident details, vendor response, and impact assessment
5. **Review Relationship:** Assess whether vendor relationship should continue

### **11.2 Vendor Incident SLAs**

- **Critical Vendors (Customer Data Access):** Notification within 24 hours of incident discovery
- **Important/Standard Vendors:** Notification within 72 hours of incident discovery

---

## **12. Vendor Termination**

### **12.1 Planned Termination**

When ending a vendor relationship:

1. **Notification:** Provide notice per contract terms
2. **Data Retrieval:** Export or verify deletion of Proxylity data held by vendor
3. **Access Revocation:** Remove vendor access to Proxylity systems
4. **Documentation:** Document termination and data handling
5. **Update Inventory:** Remove vendor from vendor inventory

### **12.2 Emergency Termination**

If immediate termination is required (e.g., security breach, unacceptable conduct):

1. **Revoke Access:** Immediately revoke vendor access to all Proxylity systems
2. **Secure Data:** Assess and secure any data held by vendor
3. **Document:** Record reason for emergency termination
4. **Legal Review:** Engage legal counsel if contract breach or dispute is likely
5. **Transition:** Activate contingency plan for vendor services

---

## **13. Exception and Override**

Exceptions to this policy require:

- Documented business justification
- Risk assessment of the exception
- Approval by Vendor Risk Approver (CEO/Founder)
- Time-limited duration with review date
- Documentation in vendor file

---

## **14. Policy Review**

This policy is reviewed:

- **Annually** at minimum
- **Upon significant vendor changes** (new critical vendor, vendor incident)
- **When regulatory requirements change**

Updates require approval by CEO/Founder.

---

## **Appendix A: Vendor Assessment Checklist**

Use this checklist when assessing new vendors:

**Security:**
- [ ] Vendor has documented security policies
- [ ] Vendor implements access controls and MFA
- [ ] Vendor encrypts data in transit and at rest
- [ ] Vendor has incident response procedures
- [ ] Vendor holds relevant certifications (SOC 2, ISO 27001) or can demonstrate equivalent controls

**Business:**
- [ ] Vendor is financially stable
- [ ] Vendor has business continuity plans
- [ ] Vendor offers acceptable SLAs
- [ ] Vendor has adequate support channels

**Contractual:**
- [ ] Data protection terms are acceptable
- [ ] Termination terms allow data retrieval
- [ ] Liability terms are reasonable
- [ ] Incident notification requirements are included

**Risk:**
- [ ] Identified risks are documented
- [ ] Mitigations are defined for identified risks
- [ ] Residual risk is acceptable
- [ ] Risk is added to Risk Register if HIGH or CRITICAL

---

## **Appendix B: Vendor Risk Assessment Template**

```
VENDOR RISK ASSESSMENT

Vendor Name: _______________
Service Provided: _______________
Assessment Date: _______________
Assessor: _______________

CLASSIFICATION
Criticality Level: [ ] Critical  [ ] Important  [ ] Standard
Data Access Level: [ ] Customer Data  [ ] Internal Data  [ ] No Data

SECURITY ASSESSMENT
Access Control: [ ] Adequate  [ ] Concerns  [ ] Inadequate
Notes: _______________

Encryption: [ ] Adequate  [ ] Concerns  [ ] Inadequate
Notes: _______________

Incident Response: [ ] Adequate  [ ] Concerns  [ ] Inadequate
Notes: _______________

Compliance/Certifications: _______________

BUSINESS ASSESSMENT
Financial Stability: [ ] Stable  [ ] Concerns  [ ] Unstable
Business Continuity: [ ] Documented  [ ] Unknown  [ ] None
SLA Offered: _______________

IDENTIFIED RISKS
1. _______________
2. _______________
3. _______________

MITIGATIONS
1. _______________
2. _______________
3. _______________

RECOMMENDATION
[ ] Approve  [ ] Approve with Conditions  [ ] Reject

Conditions (if applicable): _______________

APPROVAL
Approved By: _______________
Date: _______________
```

---

**Approved By:** Lee Harding  
**Date:** 2025-12-05
