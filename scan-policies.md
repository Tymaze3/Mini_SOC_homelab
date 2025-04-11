# 🔍 Nessus Scan Policies

This document outlines the scanning policies used within the mini-SOC homelab to ensure consistent and effective vulnerability assessments.

---

## 🧪 Scan Policy 1: Basic Network Scan
- **Targets:** All lab IPs (DC, workstation, Kali)
- **Scan Type:** Unauthenticated
- **Ports:** Top 1000 TCP/UDP
- **Plugins:** Default enabled
- **Schedule:** Weekly
- **Purpose:** Surface-level discovery of exposed services and basic misconfigs

---

## 🔐 Scan Policy 2: Credentialed Scan (Windows)
- **Targets:** Windows Domain Controller & Workstation
- **Authentication:** Local admin credentials (stored securely in Nessus)
- **Plugins Enabled:**
  - Windows Patching
  - Configuration Auditing
  - Registry Inspection
- **Schedule:** Bi-weekly or after GPO changes
- **Purpose:** Detect missing patches, misconfigurations, and compliance issues

---

## 🐧 Scan Policy 3: Kali Linux Host
- **Targets:** Kali Linux VM
- **Authentication:** SSH login with local user
- **Scan Depth:** Deep
- **Plugins:** Linux Local Checks, Kernel Security
- **Purpose:** Identify outdated packages, kernel issues, and SUID/SGID binaries

---

## 📁 Output Location
- Reports stored in: `vuln-scanning/nessus-reports/`
- Formats: `.html`, `.csv`, `.nessus` (for internal parsing)

---

## ✅ Best Practices
- Rotate scan credentials regularly
- Compare scan deltas weekly
- Re-scan immediately after any major configuration or patching change

---
