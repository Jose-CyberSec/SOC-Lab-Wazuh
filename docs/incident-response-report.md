# Incident Response Report

## Executive Summary

During testing of the Wazuh SIEM environment, multiple account manipulation events were generated from the Windows 11 endpoint to validate security monitoring capabilities.

The activities included:

- Local user creation
- User modification
- Administrator group membership changes
- User deletion
- Failed login attempts

Wazuh successfully detected and generated alerts for each event.

---

## Timeline

18:29 - User account created

18:29 - User account modified

18:36 - User added to Administrators group

18:42 - User account deleted

18:58 - Failed login attempts generated

---

## Findings

### Finding 1

User account creation detected.

Event ID:
4720

MITRE ATT&CK:
T1136 - Create Account

Severity:
Medium

---

### Finding 2

Administrator group modification detected.

Event ID:
4732

MITRE ATT&CK:
T1098 - Account Manipulation

Severity:
High

---

### Finding 3

Failed authentication attempts detected.

Event ID:
4625

MITRE ATT&CK:
T1110 - Brute Force

Severity:
Medium

---

## Conclusion

The Wazuh deployment successfully detected and logged all test activities.

The lab validated:

- Endpoint visibility
- User account monitoring
- Authentication monitoring
- Alert generation
- Threat hunting workflows
