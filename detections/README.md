## SOC Detections – Windows Endpoint

This folder contains detection logic implemented in Splunk SPL for Windows endpoint security monitoring.

### Structure
- **Brute Force:** Primary detections based on single-event thresholds
- **Correlation:** Advanced detections correlating multiple authentication events

### Analyst Levels
- Brute force detections → SOC Tier 1
- Correlation detections → SOC Tier 2

### Data Sources
- Windows Security Event Log (XML)
- Sysmon Operational Log
