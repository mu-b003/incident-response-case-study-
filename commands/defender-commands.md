# Defender Commands

This document lists the commands executed on the Ubuntu system during the investigation.

## System Preparation

```bash
sudo apt update
sudo apt upgrade -y
```

Updates the operating system.

```bash
sudo systemctl enable ssh
sudo systemctl start ssh
sudo systemctl status ssh
```

Configures and verifies the SSH service.

---

## User Management

```bash
sudo adduser Omar
id Omar
groups Omar
```

Creates and verifies the test user.

---

## Log Preparation

```bash
sudo truncate -s 0 /var/log/auth.log
sudo systemctl restart ssh
```

Clears authentication logs and restarts SSH before the simulation.

---

## Authentication Log Analysis

```bash
grep "Failed password" /var/log/auth.log
grep "Failed password" /var/log/auth.log | wc -l

grep "Accepted password" /var/log/auth.log
grep "Accepted password" /var/log/auth.log | wc -l

grep sshd /var/log/auth.log
grep "Omar" /var/log/auth.log
grep "192.168.81.129" /var/log/auth.log
```

Identifies failed logins, successful logins, SSH events, user activity, and attacker IP activity.

---

## Evidence Collection

```bash
touch incident_evidence.log
grep "192.168.81.129" /var/log/auth.log > incident_evidence.log
cat incident_evidence.log
```

Extracts and stores incident evidence.

---

## Timeline Verification

```bash
grep "192.168.81.129" /var/log/auth.log | head -1
grep "192.168.81.129" /var/log/auth.log | tail -1
```

Identifies the first and last recorded events.

---

## Session Analysis

```bash
grep "session opened" /var/log/auth.log
grep "session closed" /var/log/auth.log

last
last Omar
```

Reviews user login sessions.

---

## IOC Identification

```bash
grep -oP '(?<=from )(\d{1,3}\.){3}\d{1,3}' /var/log/auth.log | sort -u

grep "Failed password" /var/log/auth.log | awk '{for(i=1;i<=NF;i++) if($i=="from") print $(i+1)}' | sort | uniq -c | sort -nr

grep "Failed password" /var/log/auth.log | awk '{print $(NF-5)}' | sort | uniq
```

Extracts attacker IP addresses and targeted usernames.

---

## Additional Investigation

```bash
grep sudo /var/log/auth.log
grep "authentication failure" /var/log/auth.log
grep -Ei "adduser|useradd|new user" /var/log/syslog
```

Reviews administrative activity and user account creation events.

