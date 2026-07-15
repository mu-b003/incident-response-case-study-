# Executive Summary

This project presents a simulated Linux Incident Response case study conducted in a controlled laboratory environment.

The objective of this investigation was to detect, analyze, and document an SSH brute-force attack against an Ubuntu server. During the simulation, an attacker used Hydra to perform multiple password guessing attempts against the user account **Omar**.

Authentication logs confirmed five failed login attempts followed by two successful SSH logins from the attacker's IP address (**192.168.81.129**). After gaining access, the attacker performed basic system enumeration but was unable to obtain administrative privileges or access restricted files.

The investigation focused on collecting forensic evidence, analyzing authentication logs, identifying Indicators of Compromise (IOCs), reconstructing the attack timeline, and documenting the incident following standard SOC incident response practices.

This case study demonstrates practical skills in Linux log analysis, SSH investigation, evidence collection, incident documentation, and defensive security operations.

