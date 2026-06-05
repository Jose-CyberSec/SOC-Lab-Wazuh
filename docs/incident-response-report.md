# Incident Response Report

## Executive Summary

During testing of the Wazuh SIEM environment, multiple account manipulation and authentication-related events were generated from the Windows 11 endpoint to validate security monitoring capabilities.

The activities included local user creation, user modification, administrator group membership changes, user deletion, failed login attempts, and Windows service creation.

Wazuh successfully detected and generated alerts for each event, confirming endpoint visibility and security monitoring functionality.

---

## Environment

### Wazuh Server

* Hostname: `garcia-sec`
* IP Address: `192.168.230.135`

### Windows Endpoint

* Hostname: `Win11-ENDPOINT`
* IP Address: `192.168.230.136`
* Monitoring Tools: Wazuh Agent, Sysmon

---

## Timeline

| Time  | Event                              |
| ----- | ---------------------------------- |
| 18:29 | User account created               |
| 18:29 | User account modified              |
| 18:36 | User added to Administrators group |
| 18:42 | User account deleted               |
| 18:52 | New Windows service created        |
| 18:58 | Failed login attempts generated    |

---

## Findings

### Finding 1: User Account Creation

A local user account was created on the Windows endpoint.

* Windows Event ID: `4720`
* Wazuh Detection: `User account enabled or created`
* MITRE ATT&CK: `T1136 - Create Account`
* Severity: Medium

---

### Finding 2: Administrator Group Modification

A user account was added to the local Administrators group.

* Windows Event ID: `4732`
* Wazuh Detection: `Administrators Group Changed`
* MITRE ATT&CK: `T1098 - Account Manipulation`
* Severity: High

---

### Finding 3: Failed Authentication Attempts

Multiple failed login attempts were generated against the Windows endpoint.

* Windows Event ID: `4625`
* Wazuh Detection: `Logon Failure - Unknown user or bad password`
* MITRE ATT&CK: `T1110 - Brute Force`
* Severity: Medium

---

### Finding 4: User Account Deletion

A local user account was deleted from the Windows endpoint.

* Windows Event ID: `4726`
* Wazuh Detection: `User account disabled or deleted`
* MITRE ATT&CK: `T1136 - Create Account`
* Severity: Medium

---

### Finding 5: New Windows Service Created

A new Windows service was created during testing.

* Wazuh Detection: `New Windows Service Created`
* MITRE ATT&CK: `T1543 - Create or Modify System Process`
* Severity: Medium

---

## Analysis

The simulated activity resembled a common attacker workflow involving account creation, privilege escalation, possible persistence, authentication attempts, and account removal.

Wazuh successfully collected and displayed the related security events through the Threat Hunting dashboard. This confirmed that the Windows endpoint was properly enrolled and that account-management activity was visible within the SIEM.

---

## Recommendations

* Monitor all local account creation events.
* Prioritize alerts involving additions to the local Administrators group.
* Review failed authentication attempts for signs of brute force activity.
* Investigate unexpected Windows service creation events.
* Expand monitoring to Active Directory in a future lab.
* Create custom detection rules for high-risk administrative activity.

---

## Conclusion

The Wazuh deployment successfully detected and logged all test activities.

The lab validated endpoint visibility, user account monitoring, authentication monitoring, alert generation, threat hunting workflows, and basic incident response documentation.
