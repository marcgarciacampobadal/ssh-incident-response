# Incident Response Report  
## SSH Brute Force Attack Simulation

---

## 1. Executive Summary

On February 22, a series of suspicious SSH login attempts were detected on a Linux server.  
Multiple failed login attempts were observed from an external IP address (185.243.115.84), followed by a successful authentication to the `admin` account.

The pattern is consistent with a brute force attack that eventually succeeded, representing a high-severity security incident requiring immediate response.

---

## 2. Incident Description

### Date of Incident
February 22  

### Affected Service
SSH (Secure Shell)  

### Source IP
185.243.115.84 (External address)  

### Target Accounts
- root  
- admin  

The attack consisted of multiple failed authentication attempts targeting privileged accounts. After several failed attempts, the attacker successfully logged in as `admin`.

---

## 3. Log Analysis

### Suspicious Activity Identified

Example log entries:

```bash
Feb 22 08:10:01 server sshd[2001]: Failed password for root from 185.243.115.84 port 51120 ssh2
Feb 22 08:10:05 server sshd[2001]: Failed password for root from 185.243.115.84 port 51121 ssh2
Feb 22 08:10:15 server sshd[2001]: Failed password for admin from 185.243.115.84 port 51125 ssh2
Feb 22 08:11:02 server sshd[2001]: Accepted password for admin from 185.243.115.84 port 51200 ssh2
```

### Observations

- Repeated failed login attempts from the same IP address.
- Targeting of privileged accounts (`root`, `admin`).
- Successful authentication after multiple failures.
- Activity originated from an external IP address.

### Additional Normal Activity

```bash
Feb 22 09:15:33 server sshd[2010]: Accepted password for marc from 192.168.1.50 port 53000 ssh2
```

This login appears legitimate, originating from an internal IP address.

---

## 4. Risk Assessment

### Risk Level: HIGH

Reasons:

- Multiple failed authentication attempts indicate brute force behavior.
- Privileged accounts were targeted.
- A successful login occurred after repeated failures.
- Potential compromise of administrative access.

### Potential Impact

- Unauthorized access to sensitive data.
- Privilege escalation.
- Lateral movement within the network.
- Installation of malware or backdoors.

---

## 5. Containment and Mitigation Actions

### Immediate Actions

- Block source IP address (185.243.115.84) at firewall level.
- Disable or lock affected accounts.
- Reset passwords for `admin` and other privileged users.
- Review recent system activity for malicious commands.

### Recommended Security Improvements

- Implement Fail2Ban to automatically block repeated failed attempts.
- Enforce strong password policies.
- Enable Multi-Factor Authentication (MFA).
- Disable direct root SSH login.
- Restrict SSH access via firewall rules (allow only trusted IP ranges).
- Monitor logs in real-time using a SIEM solution.

---

## 6. Lessons Learned

- SSH services exposed to the internet are frequent brute force targets.
- Monitoring login attempts is critical for early detection.
- Automated protection mechanisms (rate limiting, IP banning) significantly reduce risk.
- Privileged accounts require additional hardening and monitoring.

---

## 7. Conclusion

The incident demonstrates a classic SSH brute force attack pattern that resulted in successful access to a privileged account. Immediate remediation actions are required to prevent further compromise.

This simulation highlights the importance of proactive log monitoring, incident documentation, and structured response procedures in a Security Operations Center (SOC) environment.