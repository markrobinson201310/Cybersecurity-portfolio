# Lab 1: SIEM Threat Detection with Splunk
**Author:** Mark Robinson | CompTIA Security+ | Splunk ES 8.0  
**Tools:** Splunk Free Trial, Python, Sample Log Files  
**MITRE ATT&CK Mapping:** T1110 (Brute Force), T1078 (Valid Accounts), T1046 (Network Service Scanning)

---

## Objective

Simulate real-world attack scenarios using sample log data, ingest logs into Splunk, write SPL detection queries, and build a basic security dashboard — replicating Tier 1 SOC analyst workflows.

---

## Tools Required

- Splunk 
- Python 3.x (for log generation script)
- This repository's sample log files

---

## Lab Scenarios

### Scenario 1 — Brute Force Login Detection (T1110)
Detect repeated failed login attempts from a single IP address indicating a brute force attack.

### Scenario 2 — Suspicious After-Hours Login (T1078)
Detect successful logins occurring outside business hours (10pm–6am) which may indicate compromised credentials.

### Scenario 3 — Port Scan Detection (T1046)
Detect a single source IP connecting to many destination ports in a short time window indicating reconnaissance activity.

---

## Step-by-Step Walkthrough

### Step 1 — Generate Sample Logs
Run the included Python script to generate realistic sample log data:
```bash
python3 generate_logs.py
```
This creates three log files:
- `auth_logs.csv` — authentication events
- `network_logs.csv` — network connection events  
- `system_logs.csv` — system events

### Step 2 — Ingest Logs Into Splunk
1. Open Splunk Web (http://localhost:8000)
2. Navigate to **Settings > Add Data > Upload**
3. Upload each CSV file
4. Set sourcetype to `csv` for each file
5. Confirm data appears in Search & Reporting

### Step 3 — Run SPL Detection Queries

**Brute Force Detection:**
```spl
index=main sourcetype=csv action=failed
| stats count by src_ip, user
| where count > 5
| sort -count
| rename src_ip as "Source IP", user as "Targeted User", count as "Failed Attempts"
```

**After-Hours Login Detection:**
```spl
index=main sourcetype=csv action=success
| eval hour=strftime(_time, "%H")
| where hour >= 22 OR hour <= 6
| table _time, src_ip, user, action
| rename src_ip as "Source IP", user as "Username"
| sort -_time
```

**Port Scan Detection:**
```spl
index=main sourcetype=csv event_type=connection
| stats dc(dest_port) as unique_ports by src_ip
| where unique_ports > 15
| sort -unique_ports
| rename src_ip as "Source IP", unique_ports as "Unique Ports Scanned"
```

### Step 4 — Build a Detection Dashboard
1. Run each query above
2. Click **Save As > Dashboard Panel** for each result
3. Name your dashboard: **SOC Threat Detection Dashboard**
4. Add a title and description to each panel
5. Screenshot your completed dashboard for your portfolio

### Step 5 — Document Your Findings
Use the incident report template in `/docs/incident_report_template.md` to document:
- What you detected
- Severity classification
- Recommended response actions
- MITRE ATT&CK technique mapping

---

## Expected Results

| Scenario | Detection | Severity |
| Brute Force | IP with 5+ failed logins | High |
| After-Hours Login | Successful login 10pm–6am | Medium |
| Port Scan | IP touching 15+ ports | High |

---

## Key SPL Concepts Demonstrated

- `stats count by` — aggregate events by field
- `eval` — create calculated fields
- `where` — filter results
- `dc()` — distinct count function
- `strftime` — time formatting
- `sort` — order results
- `rename` — clean up field names for reporting

---

## Incident Report Template

After completing detections, document findings using this structure:

```
INCIDENT REPORT
Date/Time Detected:
Analyst Name: Mark Robinson
Severity: [Critical/High/Medium/Low]
MITRE ATT&CK Technique:

Summary:
[Brief description of what was detected]

## What This Lab Demonstrates to Employers

- Hands-on Splunk SIEM experience
- SPL query writing for threat detection
- MITRE ATT&CK framework awareness
- Incident documentation practices
- Dashboard creation for security visibility
- Real SOC Tier 1 analyst workflows
