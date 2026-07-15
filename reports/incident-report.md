# Incident Response Report

## Incident Overview

A simulated SSH brute-force attack was conducted against an Ubuntu Linux server in a virtual lab environment. The objective was to investigate the attack from the defender's perspective and document the complete incident response process.

---

## Environment

* Attacker Machine: Kali Linux
* Target Machine: Ubuntu 26.04 LTS
* Network Type: VMware Host-Only Network
* Target Service: OpenSSH
* Target User: Omar

---

## Attack Description

The attacker first scanned the target system using Nmap and identified that SSH (Port 22) and Apache HTTP (Port 80) were accessible.

A custom password list was created and Hydra was used to perform a brute-force attack against the SSH service.

After multiple failed attempts, Hydra successfully discovered the correct password for the user **Omar**, allowing the attacker to establish an SSH session.

Once authenticated, the attacker performed several reconnaissance commands including:

* whoami
* hostname
* pwd
* id
* groups
* history
* cat /etc/passwd
* cat /etc/os-release
* uname -a

The attacker attempted privilege escalation by accessing:

* /root
* /etc/shadow

Both attempts failed due to insufficient permissions.

---

## Evidence Collected

Evidence was collected from:

* /var/log/auth.log
* /var/log/syslog
* SSH authentication records
* Session logs
* User activity
* Login history

The relevant events were exported into an evidence file for documentation.

---

## Incident Analysis

Authentication logs confirmed:

* Five failed authentication attempts.
* Two successful SSH logins.
* All connections originated from a single IP address.
* The compromised account was Omar.
* No privilege escalation occurred.
* No system configuration changes were detected.

---

## Root Cause

The attack succeeded because the user account was protected by a weak password that was included in the attacker's password list.

---

## Impact

The attacker successfully gained access to a standard user account.

No administrative privileges were obtained.

No sensitive system files were accessed.

The overall impact remained limited to a low-privileged user session.

---

## Conclusion

The incident demonstrates a successful SSH brute-force attack followed by limited post-compromise activity.

Log analysis confirmed every stage of the attack, enabling accurate reconstruction of the incident timeline and successful evidence collection.

