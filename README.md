# IAM Account Lockout Investigation (IAM-001)

## Project Overview
This project documents a simulated Windows Active Directory account lockout investigation. The objective was to analyze failed authentication events, identify a likely root cause, assess potentially suspicious activity, and recommend appropriate incident response actions.

**Disclaimer:** All accounts, devices, timestamps, and events in this case are fictional training data. This is not a production incident.

## Scenario
The account `jsmith` experienced multiple failed login attempts followed by an account lockout. Investigation suggested that an email application on workstation `WS-014` was using an outdated saved password.

A subsequent failed login attempt from an unfamiliar source remained unexplained, requiring additional security review.

## Environment and Evidence
- Simulated Windows Active Directory environment
- Windows Security Event ID 4625 — Failed logon
- Windows Security Event ID 4740 — Account lockout
- Fictional authentication event timeline in CSV format
- Analyst incident documentation in Markdown

## Investigation Process
1. Reviewed the supplied authentication events in chronological order.
2. Identified repeated failures associated with WS-014.
3. Correlated the failures with the account lockout event.
4. Considered the user's report of outdated email application credentials.
5. Flagged the unfamiliar authentication source for additional investigation.
6. Recommended validation and escalation before restoring account access.

## Key Findings
- Outdated saved credentials were the likely cause of the initial failures.
- The unfamiliar authentication attempt remains unresolved.
- No successful login from that unfamiliar source was identified in the supplied evidence.
- Account recovery remains pending security review.

## Recommended Response
Correlate additional authentication events, validate source information, verify the user's activity, and escalate unresolved suspicious activity under organizational policy.

## Project Files
- [Security Investigation Report](incident-report.md)
- [Simulated Authentication Logs](sample-authentication-logs.csv)

## Skills Demonstrated
- Security event analysis
- Authentication failure investigation
- Identity and Access Management (IAM)
- Account lockout troubleshooting
- Incident documentation
- Risk assessment and escalation
- Evidence-based security decision-making

## Lessons Learned
This exercise reinforced the importance of distinguishing likely explanations from confirmed findings, reviewing authentication events chronologically, and avoiding premature account recovery when suspicious activity remains unresolved.

## Case Status
Open — Pending Security Review

## Portfolio Disclosure
This is a fictional cybersecurity training case study, not an actual SOC investigation.
