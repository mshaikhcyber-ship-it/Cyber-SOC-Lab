# SOC Case Study

---

# 1. Executive Summary
A Password Spraying attack was detected after multiple authentication attempts targeted multiple enterprise user accounts using a limited set of commonly used passwords. The activity was identified through continuous security monitoring and triggered an investigation to determine whether any user accounts had been successfully compromised.

The investigation involved reviewing authentication logs, analyzing source IP activity, identifying affected accounts, validating account lockout events, and assessing the overall impact. No successful account compromise was confirmed during the investigation. Appropriate containment and monitoring measures were implemented to reduce future authentication-based attack risks.

> **Note:** This case study is based on a sanitized enterprise scenario. All sensitive information has been removed for educational purposes.

# 2. Attack Overview
Password Spraying is a credential-based attack in which an attacker attempts to authenticate against multiple user accounts using a small number of commonly used passwords.

Unlike a traditional brute-force attack, where many passwords are tested against a single account, Password Spraying distributes authentication attempts across many accounts. This approach helps attackers avoid account lockout policies while increasing the likelihood of compromising weak passwords.

### Common Objectives

- Gain unauthorized access to enterprise accounts
- Bypass account lockout thresholds
- Identify users with weak passwords
- Establish an initial foothold within the environment
- Perform privilege escalation or lateral movement after successful authentication

### Why It Matters

Password Spraying is commonly observed in enterprise environments and is often an early stage of larger cyber attacks, including ransomware, business email compromise (BEC), and data exfiltration campaigns.
# 3. Detection Source
| Source | Details |
|--------|---------|
| SIEM | Seceon SIEM generated an alert after detecting multiple failed authentication attempts across several user accounts from a single external source. |
| EDR | Trellix EDR was reviewed to identify any suspicious endpoint activity related to the affected accounts. No malicious endpoint execution was observed during the investigation. |
| Authentication Logs | Windows authentication logs were analyzed to verify failed logon attempts, account lockout events, and login patterns. |
| Threat Intelligence | The source IP address was checked against publicly available threat intelligence sources to identify any known malicious reputation. |
| Analyst Validation | The SOC analyst correlated authentication events, timestamps, affected users, and source information before determining the severity and next response actions. |
