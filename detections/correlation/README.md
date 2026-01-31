## Login Success After Failures – Windows Correlation

**Techniques:**  
- MITRE ATT&CK T1110 – Brute Force  
- MITRE ATT&CK T1078 – Valid Accounts  

**Data Sources:**  
- Windows Security Event Log (4625, 4624)

**Severity:** High

### Description
This correlation detects a successful Windows logon (Event ID 4624) that occurs after one or more failed logon attempts (Event ID 4625), indicating a potential credential compromise.

### Correlation Logic
- One or more failed logons (4625)
- Followed by at least one successful logon (4624)
- Grouped by user account

### Fields Used
- `user`
- `fails`
- `success`

### SOC Use Case
This detection represents a high-priority alert typically escalated from Tier 1 to Tier 2 analysts for investigation.

### Investigation Notes
- Review source IP addresses
- Correlate with Sysmon process creation (Event ID 1)
- Check logon type and authentication package

### File
`login_success_after_failures.spl`