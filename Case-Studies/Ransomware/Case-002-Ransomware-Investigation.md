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
1. Received a critical ransomware alert from Seceon SIEM indicating suspicious encryption activity across multiple endpoints.

2. Reviewed alert details, including affected hosts, user accounts, timestamps, process names, and file modification events.

3. Correlated SIEM alerts with Trellix EDR telemetry to identify the initial malicious process responsible for file encryption.

4. Verified whether the ransomware attempted lateral movement by reviewing authentication logs, SMB connections, and remote execution activities.

5. Identified Indicators of Compromise (IOCs), including suspicious file hashes, process names, command-line activity, and network connections.

6. Isolated affected endpoints using EDR containment capabilities to prevent further encryption and lateral spread.

7. Assessed the scope of impact by identifying encrypted files, affected systems, privileged accounts, and critical business assets.

8. Documented investigation findings, collected forensic evidence, and escalated the incident to the Incident Response team for containment, eradication, and recovery.
# Timeline of Events
| Time (UTC) | Event |
|------------|-------|
| 10:05 | Seceon SIEM generated a critical ransomware alert. |
| 10:07 | SOC Analyst acknowledged the incident and initiated investigation. |
| 10:12 | Trellix EDR identified suspicious encryption processes on affected endpoints. |
| 10:18 | Impact assessment confirmed multiple encrypted files on compromised systems. |
| 10:25 | Affected endpoints were isolated to prevent lateral movement. |
| 10:35 | Incident was escalated to the Incident Response team for containment and recovery. |
| 10:50 | Investigation findings and evidence were documented. |
# Evidence Collected
- Seceon SIEM ransomware alerts
- Trellix EDR detection logs
- Windows Security Event Logs
- Windows System Event Logs
- Suspicious process execution details
- File encryption activity logs
- File hash values
- Network connection logs
- Authentication logs
- Threat Intelligence lookup results
- Endpoint isolation records
# Indicators of Compromise (IOC)
| IOC Type | Value | Status |
|----------|-------|--------|
| File Hash (SHA256) | XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX | Malicious |
| Ransom Note | README.txt / RECOVER_FILES.txt | Detected |
| Encrypted File Extension | .locked / .encrypted | Confirmed |
| Suspicious Process | ransomware.exe (Example) | Detected |
| Command Line | vssadmin delete shadows | Suspicious |
| Registry Changes | Persistence Keys Modified | Observed |
| Network Connection | Suspicious External IP | Investigated |
| Endpoint Status | Isolated | Completed |	
# MITRE ATT&CK Mapping
| Technique ID | Technique | Why It Applies |
|--------------|-----------|----------------|
| T1486 | Data Encrypted for Impact | The ransomware encrypted enterprise files to disrupt business operations. |
| T1059 | Command and Scripting Interpreter | The malware executed commands to perform malicious actions on the host. |
| T1562 | Impair Defenses | Security controls may be disabled or bypassed before encryption begins. |
| T1021 | Remote Services | Attackers may use remote services to spread laterally across the environment. |
| T1078 | Valid Accounts | Compromised credentials can be used to gain and maintain unauthorized access. |
# Root Cause
The investigation determined that the ransomware attack originated after the execution of a malicious payload on an enterprise endpoint. The malware successfully initiated file encryption activity, resulting in multiple security alerts generated by endpoint protection and SIEM monitoring.

The incident highlighted weaknesses that could contribute to ransomware attacks, including compromised credentials, unpatched systems, phishing-based initial access, or unauthorized execution of malicious files. Although the exact initial access vector was not confirmed in this sanitized case study, the investigation emphasized the importance of layered security controls, endpoint protection, timely patch management, and user awareness.
# Impact Assessment
The ransomware activity impacted multiple enterprise endpoints and resulted in unauthorized file encryption. Immediate containment actions limited further propagation and reduced the overall business impact.

Potential business impacts included:

- Temporary disruption of business operations
- Loss of access to critical business files
- Risk of data exfiltration before encryption
- Financial losses due to operational downtime
- Reputational damage
- Potential regulatory and compliance implications

Based on the investigation, the incident was classified as **Critical** due to the potential business impact associated with ransomware attacks.
# Containment Actions
- Immediately isolated affected endpoints using Trellix EDR containment capabilities.
- Blocked identified Indicators of Compromise (IOCs), including malicious file hashes and suspicious IP addresses.
- Disabled compromised user accounts until the investigation was completed.
- Restricted lateral movement by reviewing SMB access, RDP sessions, and privileged account activity.
- Preserved forensic evidence before initiating cleanup activities.
- Escalated the incident to the Incident Response (IR) team for eradication and recovery.
# Remediation
- Remove the ransomware payload and any associated malicious files from affected systems.
- Restore affected systems and business data from verified, clean backups.
- Apply the latest operating system and application security patches.
- Reset passwords for affected and privileged accounts.
- Perform a complete endpoint scan to ensure no persistence mechanisms remain.
- Review and strengthen endpoint protection policies within Trellix EDR.
- Validate that Multi-Factor Authentication (MFA) is enabled for privileged and remote access accounts.
- Conduct user awareness training to reduce phishing and malware infection risks.
# Detection Improvement
To improve the detection and response to ransomware attacks, the following enhancements are recommended:

- Develop SIEM correlation rules to detect abnormal file encryption behavior across multiple endpoints.
- Enable real-time alerts for mass file modifications, shadow copy deletion, and ransomware-related command execution.
- Integrate threat intelligence feeds to automatically identify known ransomware indicators.
- Configure behavioral detection policies within Trellix EDR to identify suspicious process execution and encryption activity.
- Regularly review and tune detection rules to reduce false positives while maintaining effective threat visibility.
- Conduct ransomware simulation exercises to validate detection and incident response capabilities.
# Lessons Learned
- Early detection and rapid endpoint isolation are critical to limiting ransomware spread.
- Endpoint Detection and Response (EDR) solutions provide valuable visibility into malicious process execution and encryption behavior.
- Strong backup and disaster recovery strategies significantly reduce business impact during ransomware incidents.
- Multi-Factor Authentication (MFA), regular patch management, and user awareness training help reduce the risk of initial compromise.
- Continuous monitoring, threat hunting, and SIEM correlation rules improve the organization's ability to detect ransomware at an early stage.
# References
# Analyst Notes
Include personal observations, challenges faced during investigation, and key takeaways.
