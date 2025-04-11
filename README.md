# 🛡️ Mini SOC - Homelab Edition (Kali Linux-Based)

This repository serves as a working template for building a small-scale Security Operations Center (SOC) within a Kali Linux environment. It’s designed for hands-on learning in detection engineering, threat hunting, and incident response.

---

## 🎯 Project Goals

- Establish foundational SOC components for practical experience
- Monitor and collect logs from Kali Linux and other systems
- Deploy and integrate a vulnerability scanner (Nessus)
- Simulate and respond to common attack behaviors
- Develop detection rules, dashboards, and basic playbooks

---

## 🧱 Core Components

| Component             | Purpose                                                  |
|-----------------------|----------------------------------------------------------|
| **Syslog (rsyslog)**  | Centralized log collection from various sources          |
| **Elastic Stack (ELK)** | Log aggregation, search, correlation, dashboards       |
| **Kali Linux**        | Primary platform for SOC tools and simulations           |
| **Nessus Essentials** | Vulnerability scanning and misconfiguration auditing     |

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
│   ├── rsyslog-config.conf
│   └── elastic-agent/
├── playbooks/
│   ├── alert-response-template.md
│   └── incident-playbook.md
├── vuln-scanning/
│   ├── nessus-reports/
│   │   └── kali-initial-scan.html
│   ├── scan-policies.md
│   └── notes.md
└── dashboard-screenshots/
```

---

## 🚦 Status Tracker

- [x] Create mini-SOC repo and README.md template
- [ ] Set up log forwarding (rsyslog)
- [ ] Install and configure Elastic Stack (ELK)
- [ ] Configure Nessus for Kali scans
- [ ] Parse logs and test first alert (e.g., unauthorized access)
- [ ] Write first detection rule (Sigma format)
- [ ] Document one response playbook

---

## 🔒 Disclaimer

This mini-SOC is built in a fully isolated homelab for educational purposes only. It is not intended for use in production environments.

---
