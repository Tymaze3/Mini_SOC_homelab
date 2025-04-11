# 🛠️ Mini SOC Deployment Notes (Kali Linux-Based)

This document outlines setup steps for each component of the mini-SOC environment within a Kali Linux setup.

---

## 🔧 1. Syslog (rsyslog)

### Configure rsyslog for centralized logging:

1. Install rsyslog (if not already installed):

   ```bash
   sudo apt-get update
   sudo apt-get install rsyslog
   ```

2. Configure `/etc/rsyslog.conf` to accept remote logs:

   ```bash
   sudo nano /etc/rsyslog.conf
   ```

   Uncomment or add the following lines:

   ```bash
   module(load="imudp")
   input(type="imudp" port="514")
   module(load="imtcp")
   input(type="imtcp" port="514")
   ```

3. Restart rsyslog service:

   ```bash
   sudo systemctl restart rsyslog
   ```

---

## 🔍 2. Elastic Stack (ELK)

### Install and configure Elastic Stack:

1. Install Elasticsearch, Logstash, and Kibana:

   ```bash
   sudo apt-get install elasticsearch logstash kibana
   ```

2. Configure each component as per your requirements.

3. Start and enable services:

   ```bash
   sudo systemctl start elasticsearch
   sudo systemctl enable elasticsearch
   sudo systemctl start logstash
   sudo systemctl enable logstash
   sudo systemctl start kibana
   sudo systemctl enable kibana
   ```

4. Access Kibana at `http://localhost:5601`.

---

## 🛡️ 3. Nessus Essentials

### Install and configure Nessus:

1. Download Nessus Essentials for Debian/Kali from [Tenable's website](https://www.tenable.com/products/nessus/nessus-essentials).

2. Install the downloaded package:

   ```bash
   sudo dpkg -i Nessus-<version>-debian6_amd64.deb
   ```

3. Start Nessus service:

   ```bash
   sudo systemctl start nessusd
   ```

4. Access Nessus at `https://localhost:8834` and complete the setup.

---

## 🔄 4. Integration Notes

- Configure rsyslog to forward logs to Logstash.
- Use Logstash to parse logs and send them to Elasticsearch.
- Visualize and analyze logs using Kibana.
- Schedule regular scans with Nessus and import results into Kibana for correlation.

---

## 📁 Suggested File Paths in This Repo

```plaintext
configs/
├── rsyslog-config.conf        # Example rsyslog configuration
├── elastic-agent/             # ELK-related pipelines and filters
vuln-scanning/
├── scan-policies.md           # Description of Nessus scan profiles
├── nessus-reports/            # Exported scan reports
logs/
├── parsed-log-samples/        # Example logs for testing detections
```

---

Continue expanding this file as your SOC grows — add exact configurations, test results, screenshots, and troubleshooting notes.

---
