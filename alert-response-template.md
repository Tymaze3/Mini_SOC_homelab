# 🚨 Alert Response Playbook: PowerShell Encoded Command

## 🔔 Alert Summary
- **Alert Name:** Suspicious PowerShell Encoded Command Execution
- **Detection Rule:** `001-powershell-encoded`
- **Source:** Windows Security Log (Process Creation)
- **Severity:** High
- **MITRE ATT&CK ID:** T1059.001 (PowerShell Execution)

---

## 🧭 Investigation Steps

### 1. Identify the Host & User
- Review the alert details: Machine name, User ID, Timestamp
- Correlate with user login logs (Event ID 4624)

### 2. Examine Process Lineage
- Check ParentImage of PowerShell process
- Validate if PowerShell was launched from script, Office doc, or CMD

### 3. Extract and Decode Base64 String
- Use PowerShell or CyberChef:
  ```powershell
  [System.Text.Encoding]::UTF8.GetString([System.Convert]::FromBase64String("<base64-string>"))
  ```
- Identify script behavior: Download, recon, persistence?

### 4. Review Historical Events
- Check 5-10 minutes before/after the alert for additional signs:
  - Registry changes
  - Scheduled tasks
  - Network connections

### 5. Correlate With Threat Intel
- Look for known toolkits or patterns (Empire, PowerSploit, etc.)
- Scan the hash of the decoded payload

---

## 🔧 Containment Actions
- Disable or lock the affected user account
- Isolate the host from the network
- Notify team via incident Slack/Teams channel

---

## 🧼 Remediation Steps
- Remove persistence artifacts (scheduled tasks, services, scripts)
- Reset credentials for affected user
- Reimage if host shows signs of lateral movement or deeper compromise

---

## 📓 Notes
- Document the timeline and decisions in incident log
- Capture forensic images if required
- Store decoded script and process lineage evidence in IR folder

---

## ✅ Lessons Learned
- Add allowlisting exceptions if FP
- Tune detection to reduce noise
- Update Sigma rule with observed variants if needed

---
