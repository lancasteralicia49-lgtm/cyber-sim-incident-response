# SOC Incident 001 — Investigation Timeline

## Incident Timeline

| Time | Event | Significance |
|---|---|---|
| 16:31 | `j.smith` received a suspicious payroll-themed phishing email | Potential initial attack vector |
| 16:34 | Link in the phishing email was clicked from the company laptop | Possible credential exposure |
| 16:42–16:48 | 17 failed authentication attempts against `j.smith` | Possible credential attack |
| 16:49 | Successful authentication from `185.203.118.74` | Potential account compromise |
| 16:53 | Finance/Payroll SharePoint accessed | Sensitive resources accessed |
| 16:54 | `September_Payroll.xlsx` downloaded | Sensitive data accessed |
| 16:55 | `September_Payroll.xlsx` downloaded again | Continued suspicious activity |
| 16:56 | `Employee_Banking_Info.xlsx` downloaded | Additional sensitive data accessed |
| 16:57 | `Employee_Banking_Info.xlsx` opened | Sensitive financial information accessed |

## Additional Investigation Findings

- The suspicious session originated from an unmanaged Windows 10 device.
- The legitimate user normally uses a managed Windows 11 corporate laptop.
- The suspicious authentication did not trigger the normal MFA challenge.
- The same source IP attempted authentication against additional employee accounts.
- A total of 23 employees received the phishing email.
- Seven employees clicked the phishing link.
- Three additional accounts experienced authentication attempts from the suspicious IP.
- No additional successful authentication was identified among those accounts.

## Potential Data Exfiltration

The suspicious session established an outbound HTTPS connection to an unapproved external destination.

Approximately 18 MB of data was transferred outbound.

The available evidence suggests possible data exfiltration, but does not establish exactly what information was transferred.

## Investigation Flow

**Phishing Email → Link Clicked → Authentication Attempts → Successful Login → Payroll Access → File Downloads → Potential Data Transfer → Containment → Recovery**

## Analyst Observation

The timeline demonstrates how seemingly separate alerts can become connected when events are analyzed chronologically.

The combination of phishing activity, authentication anomalies, unusual device information, sensitive file access, and outbound network activity increased the confidence that the account had been compromised.
