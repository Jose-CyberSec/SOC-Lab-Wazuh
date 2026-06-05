# Wazuh SIEM Home Lab

![Wazuh](https://img.shields.io/badge/Wazuh-SIEM-blue)
![Sysmon](https://img.shields.io/badge/Sysmon-Installed-green)
![Ubuntu](https://img.shields.io/badge/Ubuntu-24.04-orange)
![Windows 11](https://img.shields.io/badge/Windows-11-blue)
![Status](https://img.shields.io/badge/Status-Completed-success)

## Overview

This project documents the deployment of a Wazuh Security Information and Event Management (SIEM) lab using Ubuntu Server 24.04 LTS, Windows 11 Enterprise Evaluation, Sysmon, and VMware Workstation Pro.

The objective was to build a hands-on Security Operations Center (SOC) environment for monitoring endpoints, generating security events, investigating alerts, and performing threat hunting activities.

---

## Objectives

* Deploy a Linux-based Wazuh SIEM platform
* Configure and manage Ubuntu Server
* Deploy and configure a Windows 11 endpoint
* Install and configure Sysmon
* Install and enroll the Wazuh Agent
* Generate security events
* Investigate alerts using Wazuh Threat Hunting
* Build a practical cybersecurity portfolio project

---

## Lab Environment

### Hypervisor

* VMware Workstation Pro 25H2

### Wazuh Server

* Ubuntu Server 24.04 LTS
* 4 vCPU
* 8 GB RAM
* 80 GB Storage
* NAT Networking

### Security Platform

* Wazuh Dashboard
* Wazuh Manager
* Wazuh Indexer

### Endpoint

* Windows 11 Enterprise Evaluation
* Hostname: `Win11-ENDPOINT`
* Wazuh Agent
* Sysmon
* VMware Tools

---

## Architecture

```text
+----------------------+
| Ubuntu Server 24.04  |
|      Wazuh SIEM      |
| 192.168.230.135      |
+----------+-----------+
           |
           |
           v
+----------------------+
| Windows 11 Endpoint  |
| Win11-ENDPOINT       |
| 192.168.230.136      |
| Sysmon + Wazuh Agent |
+----------------------+
```

---

## Installation Summary

### Phase 1 - Wazuh Deployment

* Created Ubuntu Server virtual machine
* Installed Ubuntu Server 24.04 LTS
* Configured networking and OpenSSH
* Updated operating system
* Installed Wazuh using the all-in-one deployment method
* Verified successful dashboard access

### Phase 2 - Endpoint Integration

* Deployed Windows 11 Enterprise virtual machine
* Installed VMware Tools
* Verified hostname and networking configuration
* Installed Sysmon
* Installed and started the Wazuh Agent
* Connected endpoint to Wazuh Manager
* Verified successful agent registration

### Phase 3 - Security Monitoring

* Collected Windows Security Events
* Collected Sysmon Events
* Generated endpoint activity
* Investigated alerts through Wazuh Threat Hunting
* Reviewed authentication events
* Validated security detections

### Phase 4 - Incident Response

* Generated security events
* Investigated alerts
* Performed threat hunting activities
* Documented findings
* Mapped activity to attacker techniques

---

## Security Events Generated

The following activities were intentionally performed to validate detections:

* Process creation activity
* Network connectivity activity
* Local user account creation
* Local user account modification
* Administrator group membership changes
* User account deletion
* Failed login attempts
* Windows service creation

---

## Detection Highlights

| Activity                      | Detection                                    |
| ----------------------------- | -------------------------------------------- |
| User account created          | User account enabled or created              |
| User account modified         | User account changed                         |
| Added to Administrators group | Administrators Group Changed                 |
| User account deleted          | User account disabled or deleted             |
| Failed authentication         | Logon Failure - Unknown user or bad password |
| Windows service creation      | New Windows Service Created                  |

---

## Threat Hunting Investigation

### Scenario

A local user account was created and later added to the local Administrators group.

### Findings

Observed security events:

* User account creation
* User account modification
* Administrator group membership change
* User account deletion
* Failed authentication attempts

Relevant Windows Event IDs:

* 4720 – User Created
* 4722 – User Enabled
* 4732 – Member Added to Local Group
* 4726 – User Deleted
* 4625 – Failed Logon

### MITRE ATT&CK Mapping

| Technique                       | ATT&CK ID |
| ------------------------------- | --------- |
| Create Account                  | T1136     |
| Account Manipulation            | T1098     |
| Valid Accounts                  | T1078     |
| Create or Modify System Process | T1543     |
| Brute Force                     | T1110     |

### Outcome

Wazuh successfully detected and logged all generated security events. Alerts were reviewed through the Threat Hunting dashboard and correlated with Windows Security Event Logs.

---

## Skills Demonstrated

### Cybersecurity

* SIEM Administration
* Security Monitoring
* Threat Hunting
* Incident Investigation
* Alert Analysis
* Detection Validation
* Endpoint Monitoring

### Systems Administration

* Linux Administration
* Windows Administration
* User Management
* Network Troubleshooting
* VMware Virtualization

### Security Tools

* Wazuh
* Sysmon
* VMware Workstation Pro
* Ubuntu Server
* Windows Event Viewer

---

## Screenshots

### Phase 1 – Wazuh Deployment

![VM Configuration](screenshots/01-vm-configuration.png)

![Ubuntu Installation](screenshots/02-ubuntu-installed.png)

![Wazuh Dashboard](screenshots/03-wazuh-dashboard.png)

### Phase 2 – Endpoint Integration

![Windows Installed](screenshots/01-windows-installed.png)

![Hostname Configuration](screenshots/02-hostname-config.png)

![Network Connectivity](screenshots/03-network-connectivity.png)

![VMware Tools Installation](screenshots/04-vmware-tools-installation.png)

![VMware Tools Installed](screenshots/05-vmware-tools-installed.png)

![VMware Tools Service](screenshots/06-vmware-tools-service.png)

![Sysmon Installed](screenshots/07-sysmon-installed.png)

![Sysmon Service Running](screenshots/08-sysmon-service-running.png)

![Sysmon Event Viewer](screenshots/09-sysmon-eventviewer.png)

![Wazuh Server IP](screenshots/10-wazuh-server-ip.png)

![Windows to Wazuh Connectivity](screenshots/11-windows-to-wazuh-ping.png)

![Wazuh Dashboard Access](screenshots/12-wazuh-dashboard-access.png)

![Agent Deployment Command](screenshots/13-agent-deployment-command.png)

![Wazuh Agent Installed](screenshots/14-wazuh-agent-installed.png)

![Agent Connected](screenshots/15-agent-connected-to-wazuh.png)

### Phase 3 – Security Monitoring

![Endpoint Identity](screenshots/16-endpoint-identity.png)

![Process Creation Test](screenshots/17-process-creation-test.png)

![Network Activity Generated](screenshots/18-network-activity-generated.png)

![Local User Created](screenshots/19-local-user-created.png)

![Process Creation Detection](screenshots/20-process-creation-detection.png)

![Account Manipulation](screenshots/21-account-manipulation.png)

![Administrator Group Change](screenshots/22-wazuh-administrator-group-change.png)

![User Account Deletion](screenshots/23-user-account-deletion-alert.png)

![Alerts Dashboard](screenshots/24-alerts.png)

![Failed Login Detection](screenshots/25-failed-login.png)

---

## Project Status

### Phase 1 – Wazuh Deployment

* [x] Ubuntu Server Installation
* [x] OpenSSH Configuration
* [x] Wazuh Installation
* [x] Dashboard Access

### Phase 2 – Endpoint Integration

* [x] Windows 11 Deployment
* [x] VMware Tools Installation
* [x] Sysmon Installation
* [x] Wazuh Agent Deployment
* [x] Endpoint Registration

### Phase 3 – Security Monitoring

* [x] Process Creation Monitoring
* [x] User Account Monitoring
* [x] Authentication Monitoring
* [x] Alert Analysis

### Phase 4 – Incident Response

* [x] Threat Investigation
* [x] Alert Validation
* [x] Threat Hunting
* [x] Incident Documentation

---

## Lessons Learned

This lab provided practical experience deploying and managing a SIEM environment, integrating endpoint telemetry, generating security events, and investigating alerts.

Key takeaways include:

* Deploying a Wazuh SIEM platform
* Configuring endpoint telemetry collection
* Using Sysmon to enhance visibility
* Investigating Windows security events
* Performing threat hunting activities
* Validating detections and alerts
* Documenting findings in a SOC-style workflow

---

## Future Enhancements

* Active Directory Integration
* Domain Controller Monitoring
* Custom Wazuh Rules
* Sigma Rule Development
* PowerShell Attack Detection
* Brute Force Attack Simulations
* Ransomware Detection Testing
* Incident Response Playbooks

---

## Author

**Jose Garcia**

U.S. Marine Corps Veteran
Cybersecurity Student – Pace University
SOC Analyst Candidate
