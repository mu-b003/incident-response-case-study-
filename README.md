# Incident Response Case Study

![Linux](https://img.shields.io/badge/Linux-Ubuntu-E95420?style=for-the-badge\&logo=ubuntu)
![SOC](https://img.shields.io/badge/SOC-Blue%20Team-blue?style=for-the-badge)
![Incident Response](https://img.shields.io/badge/Incident-Response-red?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

## Overview

This repository documents a complete **Incident Response Case Study** performed in a controlled VMware laboratory.

The purpose of this project was to investigate a simulated **SSH brute-force attack** against an Ubuntu Linux server. The investigation focused on detecting malicious authentication attempts, collecting forensic evidence, analyzing Linux authentication logs, identifying Indicators of Compromise (IOCs), reconstructing the attack timeline, and documenting the incident following Security Operations Center (SOC) practices.

---

# Objectives

* Simulate an SSH brute-force attack
* Investigate Linux authentication logs
* Detect malicious login attempts
* Identify attacker activities
* Collect digital evidence
* Build an attack timeline
* Produce an incident response report
* Recommend security improvements

---

# Lab Environment

| Component        | Details            |
| ---------------- | ------------------ |
| Virtualization   | VMware Workstation |
| Attacker Machine | Kali Linux         |
| Target Machine   | Ubuntu 26.04 LTS   |
| Target Service   | OpenSSH            |
| SSH Port         | 22                 |
| Network          | VMware Host-Only   |

---

# Attack Scenario

The attacker began by scanning the target system using **Nmap** to identify accessible network services. The scan revealed that the SSH service was available for remote access.

A password list was then created and **Hydra** was used to perform a brute-force attack against the SSH service targeting the user account **Omar**.

After several failed login attempts, the correct password was discovered and the attacker successfully authenticated through SSH.

Once connected, the attacker performed basic post-compromise enumeration, including identifying the current user, viewing system information, checking group memberships, reviewing command history, listing local files, and examining user accounts.

The attacker also attempted to access privileged resources such as **/root** and **/etc/shadow**, but both attempts failed due to insufficient permissions.

The defender later analyzed the authentication logs to reconstruct the entire attack and collect forensic evidence.

---

# Investigation Summary

The investigation confirmed:

* SSH brute-force attack
* Five failed authentication attempts
* Two successful SSH logins
* One attacker IP address
* Compromised account: Omar
* No privilege escalation
* No unauthorized root access
* Successful evidence collection

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

| Phase | Activity                      |
| ----- | ----------------------------- |
| 1     | Nmap reconnaissance           |
| 2     | SSH service discovery         |
| 3     | Password list preparation     |
| 4     | Hydra brute-force attack      |
| 5     | Successful SSH authentication |
| 6     | User enumeration              |
| 7     | System information gathering  |
| 8     | Failed privilege escalation   |
| 9     | Evidence collection           |
| 10    | Log analysis and reporting    |

---

# Evidence Collected

The investigation included analysis of:

* Authentication logs (`auth.log`)
* System logs (`syslog`)
* SSH authentication records
* User login sessions
* Command history
* User account information
* Incident evidence log

---

# MITRE ATT&CK Mapping

| Technique                    | ID        |
| ---------------------------- | --------- |
| Active Scanning              | T1595     |
| Brute Force                  | T1110     |
| Valid Accounts               | T1078     |
| Remote Services: SSH         | T1021.004 |
| Account Discovery            | T1087     |
| System Information Discovery | T1082     |
| File and Directory Discovery | T1083     |

---

# Tools Used

* VMware Workstation
* Ubuntu Linux
* Kali Linux
* OpenSSH
* Nmap
* Hydra
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
incident-response-case-study/
│
├── README.md
├── LICENSE
├── DISCLAIMER.md
│
├── commands/
├── reports/
├── evidence/
├── screenshots/
├── logs/
└── docs/
```

---

# Skills Demonstrated

* Incident Response
* Security Operations Center (SOC)
* Linux Security
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

* Five failed SSH login attempts were identified.
* Two successful SSH logins were recorded.
* All malicious activity originated from a single IP address.
* The attacker successfully accessed a standard user account.
* Attempts to escalate privileges were unsuccessful.
* Authentication logs provided sufficient evidence to reconstruct the complete attack.

---

# Security Recommendations

* Enforce strong password policies.
* Disable SSH password authentication.
* Use SSH public key authentication.
* Enable Multi-Factor Authentication (MFA).
* Deploy Fail2Ban to block brute-force attacks.
* Restrict SSH access to trusted hosts.
* Continuously monitor authentication logs.
* Integrate Linux logs into a SIEM platform.
* Review login activity regularly.

---

# Learning Outcomes

Through this project, I gained practical experience in:

* Investigating SSH brute-force attacks
* Analyzing Linux authentication logs
* Identifying Indicators of Compromise (IOCs)
* Collecting digital forensic evidence
* Reconstructing attack timelines
* Writing professional incident response reports
* Applying SOC investigation techniques in a controlled environment

---

# Disclaimer

This project was conducted in an isolated virtual laboratory for educational and defensive cybersecurity purposes only. All activities were performed on systems owned by the author within a controlled environment. No unauthorized systems or networks were targeted.
