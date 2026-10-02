# SOC Incident 001 — Incident Report

## Incident Overview

**Incident ID:** SOC-001  
**Severity:** High  
**Status:** Contained / Recovery  
**Attack Vector:** Phishing / Credential Compromise  
**Affected Account:** `j.smith`  
**Affected Data:** Payroll and employee banking information  

## Initial Alert

The SIEM generated an alert after detecting multiple failed authentication attempts against a Finance employee's account followed by a successful authentication from an unusual external source.

## Investigation Timeline

| Time | Event |
|---|---|
| 16:31 | Suspicious payroll-themed phishing email received |
| 16:34 | Link in phishing email clicked from company laptop |
| 16:42–16:48 | 17 failed authentication attempts against `j.smith` |
| 16:49 | Successful authentication from unusual external IP |
| 16:53 | Finance/Payroll SharePoint accessed |
| 16:54 | Payroll file downloaded |
| 16:55 | Payroll file downloaded again |
| 16:56 | Employee banking information downloaded |
| 16:57 | Employee banking information accessed |

## Key Indicators

- 17 failed authentication attempts followed by a successful login
- External source IP not normally associated with the user
- Unmanaged Windows 10 device
- User's normal device was a managed Windows 11 corporate laptop
- Normal MFA challenge was not triggered
- Sensitive Finance/Payroll resources were accessed
- Additional accounts were targeted from the same source IP
- Legitimate user denied performing the activity
- Phishing email was received shortly before the suspicious authentication activity

## Scope

The same phishing campaign was delivered to 23 employees.

Seven employees clicked the phishing link.

Three additional accounts experienced authentication attempts from the suspicious source IP, but no successful authentication was identified.

## Containment

The following containment measures were recommended or performed:

- Preserved relevant authentication and cloud logs
- Isolated the potentially compromised endpoint
- Revoked active sessions/tokens
- Temporarily disabled the compromised account
- Reset the user's credentials
- Enforced MFA
- Investigated the legacy authentication pathway
- Investigated additional employees who interacted with the phishing campaign
- Searched for additional authentication attempts from the suspicious IP
- Removed the phishing email from employee mailboxes

## Potential Data Exfiltration

The investigation confirmed that sensitive files were downloaded.

No evidence was found of external SharePoint sharing or external email transmission.

However, the suspicious session established an outbound HTTPS connection to an unapproved external destination, with approximately 18 MB of outbound data transferred.

This provides evidence suggesting possible data exfiltration, but additional investigation would be required to determine exactly what data was transferred.

## Recovery and Follow-Up

Recommended follow-up actions include:

- Complete recovery of the affected account and endpoint
- Continue monitoring for related activity
- Review and potentially disable the legacy authentication pathway
- Investigate all employees who clicked the phishing link
- Determine the scope of potentially exposed data
- Investigate the outbound network connection
- Block the phishing domain and associated indicators
- Complete incident documentation
- Conduct a post-incident review

## Lessons Learned

This simulation provided practice with:

- SOC alert triage
- Identifying authentication anomalies
- Building an incident timeline
- Prioritizing incidents based on evidence
- Evidence preservation
- Phishing investigation
- Account compromise investigation
- Containment
- Cloud and network investigation
- Potential data exfiltration analysis
- Incident documentation

The exercise reinforced the importance of following a structured incident-response process rather than immediately taking action without first understanding the available evidence.

## Disclaimer

This is a fictional cybersecurity simulation created for educational and portfolio purposes. No real organizations, accounts, credentials, systems, or sensitive information were used.
