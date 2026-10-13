# Security Investigation Report

**Case ID:** IAM-001  
**Report Type:** Authentication Failure and Account Lockout Investigation  
**Environment:** Simulated Windows Active Directory  
**Classification:** Training Exercise — Fictional Data  
**Status:** Open — Pending Security Review  
**Analyst:** [Your Name]  
**Date:** [Lab Completion Date]

## 1. Executive Summary
An Active Directory user account, jsmith, experienced multiple failed authentication attempts followed by an account lockout. Investigation identified an email application retaining outdated credentials after a recent password change as a likely explanation for the initial authentication failures.

Additional log analysis revealed an unsuccessful authentication attempt from an unfamiliar source after the account lockout. Although no successful authentication from this source was identified in the provided records, the activity remains unexplained and requires further investigation.

The recommended response is to validate the authentication sources, review related security events, and complete the organization's security checks before restoring account access.

## 2. Incident Details
**Affected Account:** jsmith  
**Confirmed Workstation:** WS-014  
**Internal IP Address:** 10.0.1.24  
**Unfamiliar Source:** 203.0.113.42 (documentation-only IP address)  
**Domain Controller:** DC-01

**Relevant Windows Event IDs:**
- 4625 — Failed logon
- 4740 — User account locked out

## 3. Event Timeline
| Time | Event ID | Source | Observation |
| --- | --- | --- | --- |
| 09:14:02 | 4625 | WS-014 | Failed authentication |
| 09:14:15 | 4625 | WS-014 | Failed authentication |
| 09:14:29 | 4625 | WS-014 | Failed authentication |
| 09:14:31 | 4740 | DC-01 | Account lockout recorded |
| 09:15:05 | 4625 | WS-014 | Additional failed authentication |
| 09:17:44 | 4625 | UNKNOWN | Failed authentication from unfamiliar source |

## 4. Investigation Findings
**Finding 1 — Likely cause of initial authentication failures**

The employee confirmed using workstation WS-014 and reported that an email application retained a previously used password. The timing and repeated failures from this workstation are consistent with an application attempting authentication using outdated credentials.

**Finding 2 — Unresolved authentication activity**

A failed authentication event was recorded from unfamiliar source 203.0.113.42. The source has not been validated as authorized or unauthorized. No successful authentication from this source was identified in the supplied records.

**Finding 3 — Account status**

The account remains locked pending completion of security review. No account unlock or password reset is documented as completed during this investigation.

## 5. Risk Assessment
**Assessment:** Potentially suspicious authentication activity; compromise not confirmed.

The outdated stored password provides a likely explanation for the initial account lockout. However, the unfamiliar authentication source requires additional investigation to determine whether it represents legitimate activity, a configuration issue, or an unauthorized access attempt.

Final severity should be assigned using the organization's incident classification procedures and additional evidence.

## 6. Recommended Actions
1. Review additional authentication logs to identify the source and context of the unfamiliar attempt.
2. Correlate timestamps, account activity, workstation information, and related authentication events.
3. Confirm recent sign-in activity with the affected employee using approved verification procedures.
4. Escalate unexplained or suspicious authentication activity according to organizational policy.
5. After required security checks and authorization, resolve outdated stored credentials and follow approved account recovery procedures.
6. Confirm successful authorized access and monitor for recurring authentication failures.

## 7. Outcome and Current Status
The investigation identified outdated application credentials as the likely cause of the initial account lockout. A separate authentication attempt from an unfamiliar source remains unresolved.

**Case Status:** Open — Awaiting additional investigation and security authorization.

## 8. Lessons Learned
This exercise demonstrated the importance of reviewing authentication logs chronologically, distinguishing probable causes from confirmed findings, and avoiding premature account recovery when potentially suspicious activity remains unresolved.

The investigation also reinforced the value of clear documentation, identity verification, and appropriate escalation in identity and access management operations.

---
**Portfolio Disclosure:** This report documents a simulated cybersecurity training scenario. It does not represent a production security incident or professional SOC investigation.
