# Investigation Methodology

The investigation followed a structured incident response process.

## Phase 1 – Preparation

* Configure the virtual lab.
* Enable SSH on the target.
* Create the test user.

## Phase 2 – Attack Simulation

* Discover open services using Nmap.
* Perform an SSH brute-force attack with Hydra.
* Authenticate using compromised credentials.

## Phase 3 – Evidence Collection

* Review authentication logs.
* Extract attacker-related events.
* Identify failed and successful logins.
* Preserve evidence.

## Phase 4 – Analysis

* Determine the attack source.
* Identify the compromised account.
* Analyze attacker actions.
* Verify privilege escalation attempts.

## Phase 5 – Reporting

* Build the attack timeline.
* Document Indicators of Compromise (IOCs).
* Produce the incident report.
* Recommend security improvements.

