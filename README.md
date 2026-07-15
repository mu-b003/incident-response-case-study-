# Incident Response Case Study

![Linux](https://img.shields.io/badge/Linux-Ubuntu-E95420?style=for-the-badge\&logo=ubuntu)
![SOC](https://img.shields.io/badge/SOC-Blue%20Team-blue?style=for-the-badge)
![Incident Response](https://img.shields.io/badge/Incident-Response-red?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

## Overview

This repository documents a complete **Incident Response Case Study** performed in a controlled VMware laboratory.

The objective of this project was to simulate an SSH brute-force attack against an Ubuntu server, investigate the incident from a defender's perspective, collect forensic evidence, analyze authentication logs, identify Indicators of Compromise (IOCs), reconstruct the attack timeline, and produce a professional incident report.

The project follows the workflow commonly used by Security Operations Center (SOC) analysts during security investigations.

---

# Objectives

* Simulate a real SSH brute-force attack
* Investigate authentication logs
* Detect malicious login attempts
* Identify attacker activities
* Collect digital evidence
* Build an attack timeline
* Document the incident
* Recommend security improvements

---

# Lab Environment

| Component      | Details            |
| -------------- | ------------------ |
| Virtualization | VMware Workstation |
| Attacker       | Kali Linux         |
| Target         | Ubuntu 26.04 LTS   |
| Service        | OpenSSH            |
| Web Server     | Apache2            |
| Network        | Host-Only          |

---

# Attack Scenario

The attacker first scanned the target machine using **Nmap** to identify open services.

After discovering the SSH service, a password list was created and **Hydra** was used to perform a brute-force attack against the user account **Omar**.

After multiple failed attempts, Hydra successfully authenticated using a weak password.

The attacker then connected through SSH and performed several enumeration activities including:

* User identification
* System information gathering
* User enumeration
* Permission checking
* File creation
* Access testing

The attacker attempted to access protected resources but failed because administrative privileges were not available.

Finally, the defender investigated the authentication logs to reconstruct the entire attack.

---

# Investigation Summary

The investigation confirmed the following:

* SSH Brute Force Attack
* Five failed login attempts
* Two successful SSH logins
* Single attacker IP address
* Compromised account: Omar
* No privilege escalation
* No root access
* No access to sensitive system files

---

# Indicators of Compromise (IOCs)

| Indicator        | Value            |
| ---------------- | ---------------- |
| Source IP        | 192.168.81.129   |
| Target User      | Omar             |
| Attack Type      | SSH Brute Force  |
| Service          | OpenSSH          |
| Port             | 22               |
| Operating System | Ubuntu 26.04 LTS |

---

# Attack Timeline

| Phase                | Description                 |
| -------------------- | --------------------------- |
| Initial Access       | Nmap Scan                   |
| Enumeration          | Open Services Identified    |
| Credential Attack    | Hydra Brute Force           |
| Authentication       | Successful SSH Login        |
| Post Exploitation    | User Enumeration            |
| Privilege Escalation | Failed                      |
| Evidence Collection  | Authentication Log Analysis |
| Documentation        | Incident Report             |

---

# Evidence Collected

The investigation analyzed:

* Authentication logs
* SSH daemon logs
* User login records
* Session history
* User activity
* Command history
* System information
* Incident evidence log

---

# MITRE ATT&CK Mapping

| Technique                    | ID        |
| ---------------------------- | --------- |
| Active Scanning              | T1595     |
| Brute Force                  | T1110     |
| Valid Accounts               | T1078     |
| SSH                          | T1021.004 |
| Account Discovery            | T1087     |
| System Information Discovery | T1082     |
| File and Directory Discovery | T1083     |

---

# Tools Used

* VMware Workstation
* Ubuntu Linux
* Kali Linux
* OpenSSH
* Apache2
* Hydra
* Nmap
* grep
* awk
* sort
* uniq
* wc
* history
* last
* systemctl

---

# Repository Structure

```text
incident-response-case-study
│
├── README.md
├── LICENSE
├── DISCLAIMER.md
│
├── commands
│   ├── attacker-commands.md
│   ├── defender-commands.md
│   └── command-explanations.md
│
├── reports
│   ├── executive-summary.md
│   ├── incident-report.md
│   ├── findings.md
│   └── recommendations.md
│
├── evidence
│   ├── incident_evidence.log
│   ├── auth-log-analysis.md
│   ├── timeline.md
│   └── indicators-of-compromise.md
│
├── screenshots
│
├── logs
│
└── docs
```

---

# Skills Demonstrated

* Incident Response
* Linux Security
* Blue Team Operations
* SOC Investigation
* Authentication Log Analysis
* SSH Investigation
* Threat Hunting
* Digital Forensics
* Evidence Collection
* IOC Identification
* Timeline Reconstruction
* Linux Administration
* Security Documentation
* MITRE ATT&CK Mapping

---

# Key Findings

* Five failed SSH login attempts were detected.
* Two successful SSH logins occurred after password guessing.
* All malicious activity originated from a single IP address.
* The attacker successfully accessed a standard user account.
* Attempts to access privileged resources were denied.
* Authentication logs provided sufficient evidence to reconstruct the complete attack.

---

# Security Recommendations

* Enforce strong password policies.
* Disable SSH password authentication.
* Use SSH public key authentication.
* Enable Multi-Factor Authentication (MFA).
* Deploy Fail2Ban.
* Restrict SSH access using firewall rules.
* Enable continuous log monitoring.
* Integrate logs with a SIEM platform.
* Review authentication logs regularly.

---

# Learning Outcomes

This project provided practical experience in:

* Detecting SSH brute-force attacks
* Investigating Linux authentication logs
* Identifying Indicators of Compromise
* Collecting forensic evidence
* Creating attack timelines
* Writing professional incident response reports
* Applying defensive security techniques in a SOC environment

---

## Disclaimer

This project was conducted in a controlled laboratory environment for educational and defensive cybersecurity purposes only. All attack simulations were performed on systems owned by the author within an isolated virtual network.

