# Case Study #002 – Ransomware Investigation
| Field | Value |
|-------|-------|
| Case ID | CS-002 |
| Category | Malware |
| Attack Type | Ransomware |
| Severity | Critical |
| Case Status | Under Investigation |
| MITRE ATT&CK | T1486 |
| Primary Platform | Seceon SIEM |
| Supporting Tools | Trellix EDR, Windows Security Logs |
| Analyst | Muzaffar Moosa |
| Report Version | 1.0 |


# Executive Summary
A ransomware attack was detected after multiple security alerts indicated suspicious file encryption activity across several enterprise endpoints. The incident was identified through continuous monitoring and immediately investigated to determine the scope of the attack, affected systems, and potential business impact.

The investigation focused on endpoint telemetry, security alerts, authentication events, file activity, and indicators of compromise to determine the attack timeline and containment requirements. Immediate response actions were initiated to isolate affected systems, prevent lateral movement, and support recovery efforts.

> **Note:** This case study is based on a sanitized enterprise scenario. All sensitive organizational information has been removed for educational purposes.

# Attack Overview
Ransomware is a type of malware designed to encrypt files, databases, or entire systems, preventing users from accessing their data until a ransom is paid. Modern ransomware attacks often involve data theft before encryption, allowing attackers to extort organizations by threatening to leak sensitive information.

### Common Objectives

- Encrypt business-critical systems and files
- Disrupt business operations
- Demand ransom for data recovery
- Steal sensitive information before encryption
- Move laterally to infect additional systems

### Why It Matters

Ransomware is one of the most damaging cyber threats affecting enterprises today. A successful attack can result in operational downtime, financial loss, reputational damage, regulatory penalties, and data breaches. Early detection and rapid containment are essential to minimize business impact.
# Detection Source
| Source | Details |
|--------|---------|
| SIEM | Seceon SIEM generated alerts indicating suspicious encryption activity, abnormal file modifications, and potential ransomware behavior. |
| EDR | Trellix EDR detected suspicious process execution, file encryption activity, and endpoint behavioral anomalies. |
| Windows Event Logs | Security and System logs were reviewed to identify process execution, service creation, and authentication events. |
| File Activity | Rapid file modifications, encrypted file extensions, and abnormal file access patterns were analyzed. |
| Threat Intelligence | File hashes, IP addresses, and related Indicators of Compromise (IOCs) were validated using trusted threat intelligence sources. |
| Analyst Validation | The SOC analyst correlated SIEM alerts, EDR telemetry, endpoint logs, and user activity to confirm the ransomware incident. |
# Investigation Process
Document the investigation step-by-step.
# Timeline of Events
Time	Activity
# Evidence Collected
Logs
Alerts
Screenshots
Process Tree
Command Line
Network Connections
# Indicators of Compromise (IOC)
Type	Value
IP	
Domain	
URL	
Hash	
Process	
# MITRE ATT&CK Mapping
Technique ID	Technique
# Root Cause
# Impact Assessment
# Containment Actions
# Remediation
# Detection Improvement
Explain how this attack could be detected faster or prevented in the future.

# Lessons Learned
# References
# Analyst Notes
Include personal observations, challenges faced during investigation, and key takeaways.
