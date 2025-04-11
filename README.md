# 🛡️ Mini SOC - Homelab Edition

This repository is a working template for building a small-scale Security Operations Center (SOC) inside a homelab environment. It’s designed for hands-on learning in detection engineering, threat hunting, and incident response.

---

## 🎯 Project Goals
- Build foundational SOC components for hands-on practice
- Monitor and collect logs from Windows and Linux systems
- Deploy and integrate a vulnerability scanner (Nessus)
- Simulate and respond to common attack behaviors (BOS, persistence, privilege escalation)
- Build detection rules, dashboards, and basic playbooks

---

## 🧱 Core Components
| Component | Purpose |
|----------|---------|
| **Windows Event Forwarding (WEF)** | Centralized log collection from domain-joined systems |
| **Sysmon** | Enhanced visibility into Windows behavior (processes, DNS, network) |
| **FortiClient EMS** | Endpoint telemetry and EDR-lite visibility |
| **NeQter SIEM / ELK** | Log aggregation, search, correlation, dashboards |
| **Kali Linux** | Adversary simulation, scanning, and testing |
| **Nessus Essentials** | Vulnerability scanning and misconfiguration auditing |

---

## 🛠️ Folder Structure
```plaintext
mini-soc-homelab/
├── README.md
├── deployment-notes.md
├── architecture-diagram.png (optional)
├── detections/
│   ├── sigma-rules/
│   └── sample-alerts.md
├── logs/
│   └── parsed-log-samples/
├── configs/
│   ├── sysmon-config.xml
│   ├── WEF-collector-config.md
│   └── FortiClient-EMS/
├── playbooks/
│   ├── alert-response-template.md
│   └── incident-playbook.md
├── vuln-scanning/
│   ├── nessus-reports/
│   │   └── dc-initial-scan.html
│   ├── scan-policies.md
│   └── notes.md
└── dashboard-screenshots/
```

---

## 🚦 Status Tracker
- [ ] Set up log forwarding (Sysmon, WEF)
- [ ] Install and configure SIEM (NeQter or ELK)
- [ ] Configure Nessus for DC + Workstation scans
- [ ] Parse logs and test first alert (e.g., Powershell abuse)
- [ ] Write first detection rule (Sigma format)
- [ ] Document one response playbook

---

## 🔒 Disclaimer
This mini-SOC is built in a fully isolated homelab for educational purposes only. It is not intended for use in production environments.
