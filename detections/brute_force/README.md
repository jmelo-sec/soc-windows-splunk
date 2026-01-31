## Brute Force Detection – Windows Security (Event ID 4625)

**Technique:** MITRE ATT&CK T1110 – Brute Force  
**Data Source:** Windows Security Event Log  
**Event Type:** Authentication failure  
**Severity:** Medium

### Description
This detection identifies potential brute force attacks against Windows accounts by counting multiple failed logon attempts (Event ID 4625) within a short time window.

### Detection Logic
- Event ID: 4625 (failed logon)
- Threshold: ≥ 3 failures within 5 minutes
- Grouped by: user and source IP

### Fields Parsed
- `user`
- `ip`
- `fails`

### SOC Use Case
This detection is typically handled by SOC Tier 1 analysts as an initial alert indicating suspicious authentication behavior.

### Limitations
- Does not confirm account compromise
- False positives possible for mistyped passwords

### File
`brute_force_xml_4625.spl`