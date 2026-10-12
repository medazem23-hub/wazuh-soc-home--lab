# Detection Scenario : Multiple Failed Logins

## Objective

Investigate repeated failed Windows login attempts using Wazuh.

## Environment

- Wazuh Server: Ubuntu Server 24.04 LTS
- Endpoint: Windows 11
- Agent: `win11-vm`
- Windows Event ID: `4625`

## Detection

Multiple failed login attempts will be simulated on the Windows test machine. Wazuh alerts will be reviewed to determine whether the activity indicates a possible brute-force pattern.

## Investigation

The analyst will review the event timestamps, targeted account, rule IDs, and alert frequency through Wazuh Threat Hunting.

## Analyst Assessment

Repeated authentication failures may indicate suspicious activity, but additional context is required before classifying the activity as a brute-force attack.
## Investigation Findings

Three failed Windows login events were observed in Wazuh Threat Hunting.

- Agent: `win11-vm`
- Windows Event ID: `4625`
- Wazuh Rule ID: `60122`
- Rule Level: `5`
- Rule firedtimes: `3`

## Analyst Assessment

The repeated authentication failures were detected and investigated. Three failures alone do not confirm a brute-force attack; additional context is required.
## Result

To be completed after the simulation and investigation.

## Evidence

Screenshots will be added after the investigation.
