# **Proxylity LLC — Risk Register**

**Last Updated:** 2025-12-04  
**Maintained By:** Risk Owner (Lee Harding)  
**Classification:** Confidential — Internal Use Only

---

## **Overview**

This document serves as the authoritative record of Proxylity LLC's identified risks, their assessment, and mitigation status. It is updated at minimum quarterly and immediately upon identification of new risks or triggering events.

For detailed procedures, see **Proxylity LLC — Risk Management Policy**.

---

## **Risk Register**

| Risk ID | Title | Description | Impact | Likelihood | Level | Strategy | Mitigation Action | Owner | Target Date | Status | Last Updated |
|---------|-------|-------------|--------|-----------|-------|----------|-------------------|-------|-------------|--------|--------------|
| RK-001 | Multi-region AWS outage | Simultaneous failure of multiple AWS regions where Proxylity infrastructure is deployed (us-west-2, us-east-1, eu-west-1) | Catastrophic | Remote | HIGH | Reduce | Maintain automated multi-region failover; document recovery procedures; test quarterly | Lee Harding | Ongoing | Open | 2025-12-04 |
| RK-002 | GitHub service unavailability | GitHub becomes unavailable for extended period, blocking software development and deployment activities | Major | Remote | HIGH | Transfer / Reduce | Maintain repository mirrors in internal git system; maintain tested cut-over plan for source control recovery | Lee Harding | 2025-03-31 | In Progress | 2025-12-04 |
| RK-003 | Security breach or unauthorized access | Unauthorized access to production systems, customer configuration data, or AWS account | Catastrophic | Possible | CRITICAL | Reduce | Implement least-privilege IAM; maintain MFA; implement CloudWatch monitoring; annual security training; incident response plan in place | Lee Harding | Ongoing | Open | 2025-12-04 |
| RK-004 | Key dependency vulnerability | Critical vulnerability discovered in production dependencies (Lambda runtime, Python libraries, AWS services) | Major | Possible | HIGH | Reduce | Implement automated dependency scanning; maintain patching procedures; subscribe to security advisories; test patches before deployment | Lee Harding | 2025-06-30 | Open | 2025-12-04 |
| RK-005 | Loss of AWS account or Marketplace entitlement | AWS account is compromised, suspended, or AWS Marketplace entitlement is revoked | Major | Very Remote | MEDIUM | Transfer / Reduce | AWS account secured with MFA; billing contact separation; monitor AWS Health Dashboard; maintain backup AWS account plan (future) | Lee Harding | 2025-12-31 | Open | 2025-12-04 |
| RK-006 | Data corruption in DynamoDB | Customer configuration data is corrupted, deleted, or becomes inaccessible due to software bug, misconfiguration, or AWS issue | Major | Remote | HIGH | Reduce | Cross-region replication implemented (us-west-2, us-east-1, eu-west-1); point-in-time recovery enabled; test backup and restore procedures quarterly | Lee Harding | Ongoing | Complete | 2025-12-04 |
| RK-007 | CI/CD pipeline failure | CI/CD pipeline fails, blocking deployments; unable to release fixes or new features | Major | Remote | HIGH | Reduce | Scripts in each repo enable local deployment via CloudShell or local machine if needed; test recovery quarterly | Lee Harding | Ongoing | Complete | 2025-12-04 |
| RK-008 | Single point of failure in knowledge | Founder/CEO is single point of knowledge for system architecture, operations, and critical procedures; organization has no continuity plan | Major | Likely | HIGH | Reduce | Document architecture and procedures; ensure key decision procedures are documented; plan knowledge transfer as team grows | Lee Harding | 2025-12-31 | In Progress | 2025-12-04 |
| RK-009 | Regulatory compliance gap | Failure to meet compliance requirements; customer contracts specify compliance attestations (e.g., SOC 2) that Proxylity does not meet | Major | Likely | HIGH | Reduce | Develop SOC 2 compliance roadmap; implement required controls; plan SOC 2 audit for 2026; document compliance status | Lee Harding | 2026-06-30 | In Progress | 2025-12-04 |
| RK-010 | DNS service failure | Route53 or DNS resolution fails; customers cannot reach Proxylity endpoints | Major | Very Remote | MEDIUM | Transfer / Reduce | Monitor Route53 health; consider secondary DNS provider (future); maintain DNS failover plan | Lee Harding | 2025-12-31 | Open | 2025-12-04 |
| RK-011 | Customer data breach perception | Security incident occurs or is publicly reported; customer confidence is damaged regardless of actual impact | Major | Possible | HIGH | Reduce | Maintain incident response plan; develop customer communication templates; monitor security landscape; respond quickly to incidents | Lee Harding | Ongoing | Open | 2025-12-04 |
| RK-012 | Configuration data exposure | Customer configuration data (IP allow-lists, ARNs, etc.) is exposed or leaked | Major | Remote | HIGH | Reduce | Encryption at rest (KMS) and in transit (TLS 1.2+) implemented; logical separation by AWS account ID and IAM permissions enforced; access monitoring in place | Lee Harding | Ongoing | Complete | 2025-12-04 |
| RK-013 | Unpatched customer impact | Customer detects a bug or vulnerability before Proxylity can deploy a fix; results in customer data loss or service disruption | Moderate | Possible | MEDIUM | Reduce | Rapid patching and emergency deployment capability implemented; develop customer communication templates and process for critical issues | Lee Harding | 2025-12-31 | In Progress | 2025-12-04 |

---

## **Risk Trend Summary**

| Risk Level | Count | Trend | Actions |
|-----------|-------|-------|---------|
| CRITICAL | 1 | Stable | Monitor security breach risk continuously; maintain controls |
| HIGH | 8 | Decreasing | Implement mitigations; on track for Q2 2026 |
| MEDIUM | 4 | Stable | Monitor; mitigate as resources allow |
| LOW | 0 | — | None currently |

---

## **Recent Changes**

| Date | Change | Risk ID(s) | Reason |
|------|--------|-----------|--------|
| 2025-12-04 | Initial Risk Register created | RK-001 through RK-013 | Formal risk management program launched; baseline assessment completed |

---

## **Notes for Risk Approver**

- RK-003 (Security Breach) is CRITICAL; continuous monitoring required
- RK-008 (Knowledge Concentration) and RK-009 (Compliance) are HIGH priority; both have target dates in 2025 or early 2026
- Most HIGH risks have target mitigation dates within 6 months
- Recommend quarterly review to track progress on mitigations

---

## **How to Use This Register**

1. **Adding a Risk:** When a new risk is identified, create a new row with a unique Risk ID (next ID would be RK-014)
2. **Updating Status:** When mitigation action completes, update the Status column and Last Updated date
3. **Review Meetings:** Use this table as the agenda for quarterly risk review meetings
4. **Escalation:** If any risk changes to CRITICAL or HIGH, notify Risk Approver immediately
5. **Archive:** Risks with Status "Closed" can be moved to a historical archive after 1 year of closure

---

**Maintained By:** Lee Harding (Risk Owner)  
**Last Updated:** 2025-12-04
