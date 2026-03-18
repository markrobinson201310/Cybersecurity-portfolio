# 🔐 Cybersecurity Portfolio
**Mark Robinson**  
CompTIA Security+ | Google Cybersecurity Certificate | Splunk ES 8.0  
📧 Markrobinson201310@gmail.com | 📍 West Haven, CT

---

## About This Portfolio

This repository contains hands-on cybersecurity labs demonstrating core SOC analyst skills including SIEM threat detection, network traffic analysis, and incident response. Each lab simulates real-world attack scenarios and follows industry-standard frameworks including NIST SP 800-61 and MITRE ATT&CK.

These labs were built to complement formal certifications with practical, demonstrable skills relevant to Tier 1 SOC Analyst, Security Analyst, and IT Security roles.

---

## 🧪 Labs

### [Lab 1 — SIEM Threat Detection with Splunk](./lab1-siem-detection/)
Simulate real attack scenarios, generate log data, write SPL detection queries, and build a security dashboard in Splunk.

**Skills:** Splunk ES, SPL queries, SIEM dashboard creation, threat detection  
**MITRE:** T1110 (Brute Force), T1078 (Valid Accounts), T1046 (Port Scanning)

---

### [Lab 2 — Network Traffic Analysis](./lab2-network-analysis/)
Analyze simulated network traffic to detect port scans, data exfiltration, and C2 communication patterns.

**Skills:** Network analysis, anomaly detection, Python scripting, security reporting  
**MITRE:** T1046 (Network Scanning), T1048 (Exfiltration), T1071 (C2 Protocol)

---

### [Lab 3 — Incident Response Simulation](./lab3-incident-response/)
Walk through a complete phishing-to-ransomware incident response following the NIST SP 800-61 lifecycle.

**Skills:** IR lifecycle, severity classification, IOC documentation, playbook execution  
**MITRE:** T1566 (Phishing), T1078 (Valid Accounts), T1486 (Ransomware)

---

## 🛠️ Technical Skills Demonstrated

| Skill | Tools / Frameworks |
|-------|-------------------|
| SIEM Operations | Splunk ES 8.0, SPL |
| Threat Detection | Custom detection rules, threshold tuning |
| Network Analysis | Traffic analysis, anomaly detection |
| Incident Response | NIST SP 800-61, playbook execution |
| Scripting | Python 3, Bash |
| Frameworks | MITRE ATT&CK, NIST CSF |
| Documentation | Incident reports, IOC tracking, runbooks |

---

## 📜 Certifications

- ✅ CompTIA Security+
- ✅ Google Cybersecurity Certificate
- ✅ Splunk Fundamentals 1
- ✅ Splunk ES 8.0 Updates for SOC

---

## 🚀 How To Run The Labs

### Prerequisites
```bash
# Python 3.x required
python3 --version

# Install dependencies (none required beyond standard library)
```

### Lab 1 — SIEM Detection
```bash
cd lab1-siem-detection
python3 generate_logs.py
# Then follow README.md to ingest logs into Splunk
```

### Lab 2 — Network Analysis
```bash
cd lab2-network-analysis
python3 network_analyzer.py
```

### Lab 3 — Incident Response
```bash
cd lab3-incident-response
python3 incident_response.py
```

---

## 📁 Repository Structure

```
cybersecurity-portfolio/
├── README.md
├── lab1-siem-detection/
│   ├── README.md
│   └── generate_logs.py
├── lab2-network-analysis/
│   ├── README.md
│   └── network_analyzer.py
└── lab3-incident-response/
    ├── README.md
    └── incident_response.py
```

---

## 📬 Contact

I am actively seeking entry-level SOC Analyst, Security Analyst, and IT Support roles.  
Feel free to reach out via email or connect on LinkedIn.

**Email:** Markrobinson201310@gmail.com  
**Phone:** (203) 570-6570  
**Location:** West Haven, CT (Remote friendly)
