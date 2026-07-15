# Investigation Findings

## Indicators of Compromise

| Indicator        | Value            |
| ---------------- | ---------------- |
| Source IP        | 192.168.81.129   |
| Attack Type      | SSH Brute Force  |
| Target User      | Omar             |
| Target Service   | OpenSSH          |
| Port             | 22               |
| Operating System | Ubuntu 26.04 LTS |

---

## Authentication Summary

* Failed Login Attempts: **5**
* Successful Logins: **2**
* Privilege Escalation: **Not Successful**
* Unauthorized Root Access: **Denied**
* Access to /etc/shadow: **Denied**

---

## Attacker Activities

After authentication, the attacker performed:

* User identification
* System enumeration
* Operating system discovery
* User account enumeration
* Command history review
* File creation
* Permission testing

---

## Forensic Evidence

Evidence confirms that all malicious activity originated from the same IP address.

Authentication logs recorded:

* Failed password attempts
* Successful authentication
* Session creation
* Session termination
* SSH daemon events

---

## Security Assessment

Risk Level: **Medium**

Reason:

The attacker successfully authenticated using valid credentials but failed to elevate privileges or compromise protected system resources.

