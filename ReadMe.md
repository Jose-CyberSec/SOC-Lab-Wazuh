# Wazuh SIEM Home Lab

## Overview

This project documents the deployment of a Wazuh Security Information and Event Management (SIEM) platform using Ubuntu Server 24.04 LTS running in VMware Workstation Pro.

The purpose of this lab is to gain hands-on experience with Linux administration, virtualization, SIEM deployment, security monitoring, and Security Operations Center (SOC) technologies commonly used in enterprise environments.

---

## Objectives

* Deploy a Linux-based SIEM platform
* Configure and manage Ubuntu Server
* Install and configure Wazuh
* Gain experience with security monitoring technologies
* Build a practical cybersecurity portfolio project

---

## Lab Environment

### Hypervisor

* VMware Workstation Pro 25H2

### Virtual Machine Configuration

* Ubuntu Server 24.04 LTS
* 4 vCPU
* 8 GB RAM
* 80 GB Storage
* NAT Networking

### Security Platform

* Wazuh Dashboard
* Wazuh Manager
* Wazuh Indexer

---

## Installation Summary

1. Created an Ubuntu Server virtual machine in VMware Workstation.
2. Installed Ubuntu Server 24.04 LTS.
3. Configured networking and OpenSSH.
4. Updated the operating system.
5. Installed Wazuh using the all-in-one deployment method.
6. Verified successful installation and dashboard access.

---

## Skills Demonstrated

* Virtualization
* Linux Administration
* Network Configuration
* SIEM Deployment
* Security Monitoring
* OpenSSH Configuration
* Cybersecurity Lab Development

---

## Screenshots

### VMware Virtual Machine Configuration

![VM Configuration](screenshots/01-vm-configuration.png)

### Ubuntu Server Verification

Shows successful Ubuntu installation, resource allocation, hostname configuration, IP addressing, and operating system verification.

![Ubuntu Server Verification](screenshots/02-ubuntu-installed.png)

### Wazuh Dashboard

Demonstrates successful deployment of the Wazuh SIEM platform and access to the management dashboard.

![Wazuh Dashboard](screenshots/03-wazuh-dashboard.png)

---

## Project Status

### Phase 1 – Wazuh Deployment

* [x] Ubuntu Server Installation
* [x] OpenSSH Configuration
* [x] Wazuh Installation
* [x] Dashboard Access

### Phase 2 – Endpoint Integration

* [ ] Windows 11 VM Deployment
* [ ] Sysmon Installation
* [ ] Wazuh Agent Deployment

### Phase 3 – Security Monitoring

* [ ] Failed Login Detection
* [ ] PowerShell Monitoring
* [ ] File Integrity Monitoring
* [ ] Alert Analysis

### Phase 4 – Incident Response

* [ ] Threat Investigation
* [ ] Incident Documentation
* [ ] Detection Tuning
* [ ] SOC Case Study

---

## Future Enhancements

* Deploy Windows 11 endpoint
* Integrate Sysmon logging
* Configure Wazuh agents
* Generate and investigate security events
* Perform threat hunting exercises
* Develop incident response reports

---

## Author

Jose Garcia

U.S. Marine Corps Veteran | Cybersecurity Student | SOC Analyst Candidate
