# Mini Incident Response Plan

**Cyber Security Internship Track — Week 4**
**Author:** Muhammad Hamza
**Date:** July 2026
**Company:** VortexTech Online Store (Fictional Company)

---

## 1. Introduction

This document presents a structured incident response plan for a hypothetical cybersecurity breach at VortexTech Online Store.

The plan follows the six phases of the NIST Incident Response Lifecycle:

1. Preparation
2. Detection and Analysis
3. Containment
4. Eradication
5. Recovery
6. Lessons Learned

The purpose of this plan is to help the organization respond quickly, reduce the impact of the breach, protect affected customers, restore normal operations, and prevent similar incidents in the future.

> **Note:** VortexTech is a fictional company, and this breach scenario is created only for educational purposes.

---

# 2. Breach Scenario

VortexTech Online Store is a fictional e-commerce company that stores customer information and processes online orders.

The company recently deployed a new customer API endpoint. Due to a configuration mistake, the API endpoint did not properly verify whether a user was authorized to access customer records.

An attacker discovered the unsecured API endpoint and accessed customer information without permission.

The information potentially exposed included:

* Customer names
* Email addresses
* Phone numbers
* Delivery addresses
* Order information

No payment card information or customer passwords were stored in the exposed API response.

The incident was discovered when the company's security monitoring system detected an unusually large number of API requests from an unknown IP address. The security team reviewed the logs and found that the requests were accessing customer records at a much higher rate than normal.

The incident was classified as a **high-severity data exposure incident** because sensitive customer information may have been accessed.

---

# 3. Incident Response Team

The following team members would be responsible for managing the incident:

| Role                      | Responsibility                                         |
| ------------------------- | ------------------------------------------------------ |
| Incident Response Manager | Coordinates the response and makes important decisions |
| Security Analyst          | Investigates logs, alerts, and suspicious activity     |
| System Administrator      | Isolates affected systems and restores services        |
| Software Development Team | Fixes the vulnerable API endpoint                      |
| Legal and Compliance Team | Reviews notification and legal requirements            |
| Communications Team       | Prepares customer and public communications            |
| Company Management        | Provides approval and organizational support           |

---

# 4. Phase 1 — Preparation

Preparation includes the security controls, people, tools, and procedures that should already be in place before an incident occurs.

Before the breach, VortexTech should have:

* A documented incident response policy
* A trained incident response team
* Clearly assigned security roles and responsibilities
* Centralized security logging
* API activity monitoring
* Automated alerts for unusual activity
* Secure and regularly tested backups
* A process for reporting security incidents
* A communication plan for employees, customers, and management
* Regular security testing of applications and APIs
* Strong authentication and authorization controls

The company should also conduct regular incident-response exercises so employees understand what to do during a security incident.

---

# 5. Phase 2 — Detection and Analysis

## Detection

The breach was detected by the security monitoring system.

The monitoring system generated an alert after detecting:

* A large number of API requests in a short period
* Requests coming from an unfamiliar IP address
* Unusual access to many customer records
* API activity outside normal customer behavior

A security analyst reviewed the alert and reported the incident to the Incident Response Manager.

## Initial Analysis

The security team would perform the following actions:

1. Review API access logs.
2. Identify the suspicious IP address.
3. Determine when the suspicious activity started.
4. Identify which API endpoint was accessed.
5. Check how many customer records may have been exposed.
6. Review the API configuration.
7. Determine whether the attacker accessed, copied, changed, or deleted data.
8. Check whether other systems were affected.
9. Preserve logs and evidence for further investigation.
10. Record all actions and findings in an incident log.

The team would classify the incident as **High Severity** because customer personal information may have been exposed.

---

# 6. Phase 3 — Containment

The purpose of containment is to stop unauthorized access and prevent the incident from becoming worse.

## Immediate Containment Actions

The security team would:

1. Temporarily disable the vulnerable API endpoint.
2. Block the suspicious IP address at the firewall.
3. Revoke and replace affected API keys.
4. Disable any suspicious user accounts.
5. Restrict access to customer data.
6. Preserve system logs and other evidence.
7. Monitor the application for additional suspicious activity.

## Short-Term Containment

The company would:

* Add temporary authentication checks to the API.
* Limit the number of API requests allowed from one user or IP address.
* Restrict API access to authorized users only.
* Increase monitoring of customer-data systems.
* Review other API endpoints for similar security problems.

The company would avoid deleting logs or restarting systems before important evidence had been collected.

---

# 7. Phase 4 — Eradication

The purpose of eradication is to remove the root cause of the breach and eliminate any unauthorized access.

The development and security teams would:

1. Identify the API authorization error.
2. Correct the vulnerable API code.
3. Add server-side authentication checks.
4. Add authorization checks before returning customer information.
5. Remove any unauthorized access mechanisms.
6. Revoke compromised API keys and create new keys.
7. Review application configurations.
8. Scan affected systems for malware or unauthorized changes.
9. Review other API endpoints for similar vulnerabilities.
10. Perform security testing before deploying the fix.

The corrected API would be tested in a separate testing environment before being returned to production.

---

# 8. Phase 5 — Recovery

The purpose of recovery is to safely restore normal business operations.

The company would:

1. Deploy the corrected API endpoint.
2. Verify that authentication is working correctly.
3. Verify that users can access only their own information.
4. Test the application for normal functionality.
5. Restore affected data from verified backups if necessary.
6. Monitor API activity closely after restoration.
7. Check logs for repeated attack attempts.
8. Confirm that no unauthorized access is continuing.
9. Gradually return the system to normal operation.

The security team would continue enhanced monitoring for at least several days after recovery.

The incident would only be considered fully resolved after the security team confirmed that:

* The vulnerable endpoint was fixed.
* Unauthorized access had stopped.
* The application was operating normally.
* No additional systems were affected.

---

# 9. Phase 6 — Lessons Learned

After the incident, the company would hold a post-incident review.

The review would include:

* What happened?
* When did the incident begin?
* How was the incident detected?
* How quickly did the team respond?
* What customer information was exposed?
* Which security controls failed?
* Which response actions worked well?
* What problems occurred during the response?
* How can future incidents be prevented?

## Expected Findings

The review would likely conclude that:

* The API was deployed without sufficient authorization testing.
* Security testing was not completed before deployment.
* API access controls were not properly reviewed.
* Monitoring successfully detected unusual activity.
* The incident response team contained the issue quickly.

## Improvements

The company would:

* Add mandatory API security reviews.
* Improve security testing before deployment.
* Provide secure API development training.
* Improve monitoring and alert rules.
* Conduct regular incident-response exercises.
* Update the incident response plan based on lessons learned.

---

# 10. Internal Communication Plan

| Time                      | Person or Team Notified              | Information Shared                                                    |
| ------------------------- | ------------------------------------ | --------------------------------------------------------------------- |
| Immediately               | Incident Response Manager            | Initial security alert and suspected data exposure                    |
| Within 15 minutes         | Security Team                        | Incident details and investigation responsibilities                   |
| Within 30 minutes         | Company Management                   | Incident severity, possible impact, and current response              |
| Within 1 hour             | System Administrators and Developers | Technical details and required containment actions                    |
| Within 2 hours            | Legal and Compliance Team            | Possible data exposure and notification requirements                  |
| After investigation       | Communications Team                  | Confirmed facts for customer communication                            |
| After impact is confirmed | Affected Customers                   | What happened, what information was affected, and recommended actions |
| When legally required     | Relevant Authorities or Regulators   | Required incident information according to applicable laws            |

All communication should be accurate, approved, and based on confirmed information.

Employees should not share unverified information publicly or on social media.

---

# 11. Preventative Measures

The following measures could have prevented the breach:

## 1. Strong API Authentication and Authorization

Every API endpoint should verify the identity of the user and confirm that the user has permission to access the requested information.

Authorization checks should be performed on the server and should not depend only on the user interface.

## 2. Security Testing Before Deployment

All new APIs should undergo security testing before being deployed.

Testing should include:

* Authentication testing
* Authorization testing
* Access-control testing
* Input validation
* API configuration reviews

## 3. Continuous Monitoring and Rate Limiting

The company should monitor API activity and automatically detect unusual behavior.

Rate limiting should be used to reduce the number of requests that a user or IP address can make in a specific period.

---

# 12. Conclusion

This incident response plan demonstrates how VortexTech Online Store would respond to a customer data exposure caused by an unsecured API endpoint.

The response follows six phases:

1. Preparation
2. Detection and Analysis
3. Containment
4. Eradication
5. Recovery
6. Lessons Learned

A fast and organized response can reduce damage, protect customers, restore business operations, and prevent similar incidents.

The main lessons from this scenario are:

* Secure every API endpoint.
* Enforce authentication and authorization on the server.
* Monitor systems for unusual activity.
* Test applications before deployment.
* Maintain a clear incident response plan.
