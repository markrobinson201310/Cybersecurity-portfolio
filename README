# Lab 3: Incident Response Simulation
**Author:** Mark Robinson | CompTIA Security+  
**Tools:** Python  
**Framework:** NIST SP 800-61 Incident Response Lifecycle  
**MITRE ATT&CK Mapping:** T1566 (Phishing), T1078 (Valid Accounts), T1486 (Data Encrypted for Impact)

---

## Objective

Simulate a realistic phishing-to-ransomware incident response scenario, walking through each phase of the NIST incident response lifecycle: Preparation, Detection, Containment, Eradication, Recovery, and Lessons Learned.

---

## Scenario Overview

**Incident:** A user at ACME Corp receives a phishing email, clicks a malicious link, and unknowingly installs malware. The malware establishes persistence, moves laterally, and begins encrypting files.

**Your Role:** Tier 1 SOC Analyst responsible for initial triage, escalation, and documentation.

---

## Step-by-Step Walkthrough

### Phase 1 — Preparation
Before any incident occurs, ensure:
- Incident response plan is documented
- Contact lists are current
- Tools are deployed (SIEM, EDR, ticketing)
- Runbooks exist for common scenarios

### Phase 2 — Detection & Analysis
Run the incident response simulator:
```bash
python3 incident_response.py
```

The script will walk you through:
1. Initial alert triage
2. Severity classification
3. IOC identification
4. Escalation decision

### Phase 3 — Containment
Actions to take:
- Isolate affected host from network
- Reset compromised credentials
- Block malicious IP/domain at firewall
- Preserve forensic evidence

### Phase 4 — Eradication
- Remove malware from affected systems
- Patch exploited vulnerabilities
- Verify no persistence mechanisms remain

### Phase 5 — Recovery
- Restore from clean backups
- Monitor for re-infection
- Gradually restore services

### Phase 6 — Lessons Learned
- Document timeline
- Root cause analysis
- Process improvements
- Update detection rules

---

## NIST IR Lifecycle Reference

```
PREPARATION → DETECTION → CONTAINMENT → ERADICATION → RECOVERY → LESSONS LEARNED
     ↑                                                                    |
     └────────────────────────────────────────────────────────────────────┘
```

---

## Key Skills Demonstrated

- NIST SP 800-61 incident response framework
- Severity classification (P1-P4)
- IOC identification and documentation
- Escalation procedures
- Post-incident reporting
- MITRE ATT&CK mapping
