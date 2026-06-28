# windows-defender-firewall-investigation-lab

## Project Overview

This lab demonstrates how Windows Defender Firewall can be monitored, configured, and investigated from a SOC analyst perspective.

The objective was to understand firewall profiles, review inbound and outbound rules, create a temporary outbound firewall rule, and investigate the resulting Windows Firewall Operational logs using Event Viewer.

---

## Lab Objectives

- Understand Windows Defender Firewall architecture
- Review Domain, Private, and Public firewall profiles
- Analyze existing inbound and outbound firewall rules
- Create a custom outbound firewall rule
- Monitor Windows Firewall Operational logs
- Validate firewall events using Event Viewer
- Document findings from a SOC analyst perspective

---

## Lab Environment

| Component | Details |
|-----------|----------|
| Operating System | Windows 10 x64 |
| Virtualization | VMware Workstation Player |
| Security Product | Windows Defender Firewall |
| Investigation Tool | Event Viewer |
| Log Source | Windows Firewall With Advanced Security |

---

# Tools Used

- Windows Security
- Windows Defender Firewall with Advanced Security
- Event Viewer
- Windows Firewall Operational Logs

---

# Lab Workflow

## Step 1

Opened Windows Security

---

## Step 2

Verified firewall status for

- Domain Network
- Private Network
- Public Network

Confirmed Firewall was enabled on all profiles.


---

## Step 3

Reviewed Allowed Applications

Verified applications permitted through Windows Defender Firewall.


---

## Step 4

Opened

Windows Defender Firewall with Advanced Security

Reviewed

- Inbound Rules
- Outbound Rules
- Monitoring


```


## Step 5

Created a temporary outbound firewall rule.

Configuration

| Setting | Value |
|---------|-------|
| Rule Type | Program |
| Program | notepad.exe |
| Direction | Outbound |
| Action | Block |
| Profiles | Domain, Private, Public |
| Rule Name | Block Notepad (Lab) |


---

## Step 6

Opened Event Viewer

Navigated to

Applications and Services Logs

↓

Microsoft

↓

Windows

↓

Windows Firewall With Advanced Security

↓

Firewall

Verified firewall events.


---

## Step 7

Observed Event ID 2004

The event confirmed that a new firewall rule had been added.

Captured information including

- Rule Name
- Direction
- Action
- Application Path
- Profiles
- User
- Time Created


```

---

# Investigation Summary

The lab successfully demonstrated the lifecycle of a firewall configuration change.

A temporary outbound firewall rule was created to block Notepad.exe.

Windows Firewall generated Event ID 2004 confirming successful rule creation.

The investigation showed how firewall modifications are logged and how defenders can validate administrative activity using Event Viewer.

---

# MITRE ATT&CK Mapping

| Technique | ID |
|------------|-----|
| System Information Discovery | T1082 |
| Network Service Discovery | T1046 |
| Modify Firewall | T1562.004 |

---

# Skills Demonstrated

- Windows Defender Firewall
- Firewall Rule Management
- Event Viewer Analysis
- Windows Security
- Security Log Investigation
- Windows Administration
- SOC Investigation Workflow
- Security Documentation

---

# Learning Outcomes

- Understood Windows Firewall architecture
- Created outbound firewall rules
- Investigated Windows Firewall logs
- Validated administrative firewall activity
- Documented findings using SOC methodology
