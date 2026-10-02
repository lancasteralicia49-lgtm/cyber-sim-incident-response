# SOC Incident 001 — Phishing & Account Compromise

## Scenario

A fictional healthcare organization detected multiple failed authentication attempts against a Finance employee's account, followed by a successful authentication from an unusual external source.

The account subsequently accessed sensitive payroll and employee banking information.

## Investigation

The investigation identified:

- 17 failed authentication attempts
- A successful login immediately afterward
- An unusual external IP address
- An unmanaged Windows 10 device
- No normal MFA challenge
- Access to Finance/Payroll resources
- Downloads of sensitive files
- Additional authentication attempts against other employee accounts
- A phishing email received shortly before the suspicious authentication activity
- Multiple employees who interacted with the phishing campaign

## Incident Response

The investigation followed the incident-response lifecycle:

**Detection → Triage → Investigation → Containment → Eradication → Recovery → Final Assessment**

Actions included:

- Preserving logs and evidence
- Isolating the potentially compromised endpoint
- Revoking active sessions
- Resetting credentials
- Enforcing MFA
- Investigating additional affected users
- Reviewing SharePoint activity
- Investigating network traffic
- Monitoring for additional suspicious authentication

## Key Learning

This simulation helped me practice identifying anomalies, prioritizing incidents, building an attack timeline, determining scope, and making containment decisions based on available evidence.

I learned the importance of preserving evidence, distinguishing suspicious activity from confirmed compromise, and following a structured incident-response process.

## Lessons Learned

I learned how to triage and prioritize incidents based on available evidence. I also learned how quickly an attacker can potentially move from compromised credentials to sensitive information.

The simulation helped me practice identifying anomalies, investigating the scope of a compromise, and moving through detection, investigation, containment, eradication, recovery, and final assessment.

## Disclaimer

This is a fictional cybersecurity simulation created for educational and portfolio purposes. No real organizations, accounts, credentials, systems, or sensitive information were used.
