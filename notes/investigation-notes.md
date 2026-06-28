# Investigation Notes

## Investigation Information

| Field | Value |
|--------|-------|
| Investigation Title | Windows Defender Firewall Rule Investigation |
| Date | 28 June 2026 |
| Platform | Windows 10 x64 |
| Security Component | Windows Defender Firewall with Advanced Security |
| Log Source | Microsoft-Windows-Windows Firewall With Advanced Security |
| Investigation Tool | Event Viewer |
| Analyst | Abhinav Kishore |

---

# Investigation Objective

Investigate Windows Defender Firewall configuration, analyze firewall rules, create a temporary outbound firewall rule, and verify firewall configuration changes through Windows Firewall Operational logs.

---

# Scope

This investigation focused on:

- Reviewing Windows Defender Firewall status
- Verifying firewall profiles
- Examining inbound rules
- Examining outbound rules
- Creating a temporary outbound firewall rule
- Investigating generated firewall events
- Validating firewall logging

---

# Investigation Timeline

| Step | Activity |
|------|----------|
| 1 | Opened Windows Security |
| 2 | Verified Domain, Private and Public firewall profiles |
| 3 | Reviewed Allowed Applications |
| 4 | Opened Windows Defender Firewall with Advanced Security |
| 5 | Reviewed Inbound Rules |
| 6 | Reviewed Outbound Rules |
| 7 | Created temporary outbound firewall rule |
| 8 | Opened Event Viewer |
| 9 | Investigated Windows Firewall Operational Logs |
| 10 | Validated Event ID 2004 |

---

# Firewall Configuration Review

## Firewall Profiles

| Profile | Status |
|----------|--------|
| Domain | Enabled |
| Private | Enabled |
| Public | Enabled |

### Observation

All firewall profiles were enabled and actively protecting the system.

---

# Allowed Applications Review

Observed that Windows Defender Firewall contained numerous Microsoft system applications along with built-in Windows services.

No suspicious or unauthorized applications were identified.

---

# Firewall Rules Review

## Inbound Rules

Observed

- Core Networking rules
- Windows services
- Microsoft applications
- Device discovery rules

No abnormal inbound rules were identified.

---

## Outbound Rules

Observed

- Core Networking
- Microsoft 365
- Device Connectivity
- System Services

Outbound policy appeared to be in its default secure configuration.

---

# Firewall Rule Created

## Rule Information

| Property | Value |
|----------|-------|
| Rule Name | Block Notepad (Lab) |
| Rule Type | Program |
| Direction | Outbound |
| Action | Block |
| Profiles | Domain, Private, Public |
| Program | C:\Windows\System32\notepad.exe |

Purpose:

Created only for laboratory testing to understand firewall logging.

---

# Event Viewer Investigation

Navigation

Applications and Services Logs

↓

Microsoft

↓

Windows

↓

Windows Firewall With Advanced Security

↓

Firewall

---

# Event Analysis

## Event ID 2004

### Description

A new firewall rule was successfully added.

### Important Information Observed

- Rule Name
- Rule Direction
- Action
- Profiles
- Program Path
- User Account
- Timestamp

The generated event confirmed successful firewall configuration changes.

---

# Findings

✅ Firewall enabled on all network profiles

✅ No suspicious firewall rules identified

✅ Allowed applications appeared legitimate

✅ Temporary outbound rule successfully created

✅ Windows Firewall generated Event ID 2004

✅ Event Viewer accurately recorded configuration changes

---

# MITRE ATT&CK Mapping

| Technique | ID | Reason |
|------------|-----|--------|
| System Information Discovery | T1082 | Reviewing firewall configuration |
| Network Service Discovery | T1046 | Reviewing network-related services |
| Impair Defenses: Disable or Modify Firewall | T1562.004 | Demonstrated controlled firewall rule modification |

---

# Analyst Conclusion

The investigation successfully demonstrated how Windows Defender Firewall records administrative configuration changes.

Firewall Operational logs provide valuable telemetry for SOC analysts to validate firewall modifications, investigate suspicious configuration changes, and support incident response activities.
