# Lab 2: Network Traffic Analysis
**Author:** Mark Robinson 
**Tools:** Python, Wireshark (optional), PCAP sample files  
**MITRE ATT&CK Mapping:** T1046 (Network Scanning), T1071 (Application Layer Protocol), T1048 (Exfiltration)


## Objective

Analyze simulated network traffic to identify suspicious patterns including port scans, unusual data transfers, and suspicious connection behavior — core skills for any SOC analyst.


## Tools Required

- Python 3.x
- Wireshark (optional — for visual PCAP analysis)
- This repository's traffic analyzer script

---

## Lab Scenarios

### Scenario 1 — Port Scan Detection
Identify hosts scanning multiple ports across the network in a short time window.

### Scenario 2 — Large Data Transfer Detection
Identify internal hosts transferring unusually large volumes of data to external IPs — potential data exfiltration indicator.

### Scenario 3 — Suspicious Protocol Usage
Detect traffic using unusual ports or protocols that may indicate command and control (C2) communication.

---

## Step-by-Step Walkthrough

### Step 1 — Run the Traffic Analyzer
```bash
python3 network_analyzer.py
```

### Step 2 — Review the Output
The script will output:
- Summary of all connections analyzed
- Flagged suspicious hosts
- Severity ratings for each finding
- Recommended response actions

### Step 3 — Document Findings
Use the findings output to complete an incident report using the template below.

### Step 4 — Verify in Wireshark (Optional)
If you have Wireshark installed, open a PCAP file and apply these filters:
- Port scan: `tcp.flags.syn == 1 and tcp.flags.ack == 0`
- Large transfers: `tcp.len > 10000`
- Suspicious ports: `tcp.port == 4444 or tcp.port == 1337`

---

## Key Concepts Demonstrated

- Network connection analysis
- Threshold-based anomaly detection
- Data exfiltration indicators
- Port scan pattern recognition
- Security reporting and documentation
