# Attack Scenario

## Scenario Overview

This project simulates a real-world SSH brute-force attack against an Ubuntu Linux server within an isolated VMware laboratory.

The objective is to understand the complete incident response lifecycle from the defender's perspective.

## Attack Flow

1. The attacker scanned the target using Nmap.
2. The SSH service was identified as accessible.
3. A password list was prepared.
4. Hydra launched a brute-force attack against the user **Omar**.
5. Multiple authentication failures occurred.
6. The attacker successfully authenticated via SSH.
7. Basic system enumeration was performed.
8. Attempts to access privileged resources were denied.
9. Authentication logs were analyzed.
10. Digital evidence was collected and documented.

## Objective

The purpose of this scenario is to practice incident detection, forensic evidence collection, log analysis, and incident reporting in a controlled environment.

