# SSH Incident Response Simulation

## Description

This project simulates the investigation of a successful SSH brute force attack on a Linux server.

The objective is to demonstrate structured incident response procedures, log analysis, risk assessment, and mitigation recommendations — following a real-world SOC (Security Operations Center) workflow.

---

## Scenario Overview

On February 22, multiple failed SSH login attempts were detected from an external IP address. After repeated failures targeting privileged accounts, a successful login occurred.

The incident was analyzed and documented following a formal incident response structure.

---

## Project Structure

```
incident-response-simulation/
│
├── docs/
│   └── incident_report.md
│
└── README.md
```

---

## What This Project Demonstrates

- Log analysis of SSH authentication events
- Detection of brute force patterns
- Identification of suspicious IP activity
- Risk classification (High severity)
- Containment and mitigation planning
- Structured incident documentation

---

## Key Skills Showcased

- Cybersecurity fundamentals
- Blue Team mindset
- Incident response workflow
- Log interpretation
- Threat analysis
- Technical documentation

---

## Tools & Concepts

- Linux SSH logs (`auth.log` style entries)
- Brute force attack patterns
- Privileged account targeting
- Risk assessment methodology
- Security hardening recommendations

---

## Why This Matters

SSH services exposed to the internet are common attack targets.  
Being able to detect, analyze, and document such incidents is a core skill in cybersecurity roles such as:

- SOC Analyst
- Blue Team Analyst
- Incident Responder
- Cybersecurity Analyst

---

## Author

Marc Garcia Campobadal  
Cybersecurity Enthusiast | SOC Path | Blue Team Focus