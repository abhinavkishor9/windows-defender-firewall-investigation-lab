# Troubleshooting Notes

## Lab

Windows Defender Firewall Investigation

---

# Issue 1

## Windows Defender Firewall with Advanced Security does not open

### Possible Causes

- Windows Firewall service stopped
- Administrative privileges missing
- Group Policy restrictions

### Resolution

- Verify Windows Defender Firewall service is running
- Launch as Administrator
- Restart the Windows Firewall service if necessary

---

# Issue 2

## Unable to create a new firewall rule

### Possible Causes

- Standard user permissions
- Incorrect program path
- Firewall console not opened as Administrator

### Resolution

- Open Windows Defender Firewall with Advanced Security as Administrator
- Verify the executable path
- Ensure Windows Firewall service is running

---

# Issue 3

## Event ID 2004 not generated

### Possible Causes

- Rule creation unsuccessful
- Incorrect log location
- Event Viewer not refreshed

### Resolution

- Refresh Event Viewer (F5)
- Confirm rule was created successfully
- Verify Windows Firewall Operational logging is enabled

---

# Issue 4

## Unable to locate Windows Firewall Operational logs

### Correct Path

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

# Issue 5

## Firewall profiles appear disabled

### Possible Causes

- Firewall service stopped
- Third-party firewall installed
- Group Policy configuration

### Resolution

- Verify Windows Defender Firewall is enabled
- Remove conflicting third-party firewall software
- Review Group Policy settings

---

# Issue 6

## Rule created but not visible

### Possible Causes

- Viewing incorrect rule category
- Rule filtered
- Refresh required

### Resolution

- Refresh the console
- Remove active filters
- Verify whether the rule is Inbound or Outbound

---

# Issue 7

## Incorrect program path

### Example

Incorrect

```
C:\Windows\Notepad.exe
```

Correct

```
C:\Windows\System32\notepad.exe
```

---

# Issue 8

## Event Viewer showing old events

### Resolution

- Sort by Date and Time
- Refresh Event Viewer
- Filter by Event ID 2004
- Verify latest timestamps

---

# Validation Checklist

| Check | Status |
|--------|--------|
| Firewall Enabled | ✅ |
| Firewall Profiles Verified | ✅ |
| Allowed Apps Reviewed | ✅ |
| Inbound Rules Reviewed | ✅ |
| Outbound Rules Reviewed | ✅ |
| Custom Rule Created | ✅ |
| Event ID 2004 Generated | ✅ |
| Event Details Verified | ✅ |

---

# Best Practices

- Always document firewall changes.
- Use descriptive names for custom firewall rules.
- Remove temporary rules after testing.
- Regularly review inbound and outbound rules.
- Monitor Windows Firewall Operational logs for unauthorized changes.
- Validate firewall events before escalating incidents.
- Correlate firewall events with endpoint and authentication logs during investigations.

---

# Lessons Learned

- Windows Defender Firewall records administrative changes through Event Viewer.
- Event ID 2004 confirms successful firewall rule creation.
- Event Viewer is an effective source for validating firewall modifications.
- Temporary firewall rules are useful for understanding Windows security logging in a controlled lab environment.
