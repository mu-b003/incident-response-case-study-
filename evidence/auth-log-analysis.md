# Authentication Log Analysis

The authentication log (`/var/log/auth.log`) was analyzed to identify suspicious SSH activity.

## Findings

* Five failed password attempts were detected.
* Two successful SSH logins were recorded.
* All authentication events originated from the same IP address.
* The compromised account was **Omar**.
* No successful privilege escalation was identified.
* SSH sessions were properly opened and closed.

## Evidence Sources

* Failed password events
* Accepted password events
* SSH daemon logs
* Session opened events
* Session closed events
* Authentication failure messages

The authentication log provided sufficient evidence to reconstruct the complete attack sequence.

