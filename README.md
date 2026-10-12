# Wazuh SOC Home Lab

A hands-on Wazuh SOC home lab focused on Windows security monitoring, threat detection, log analysis, and incident investigation.

## Project Overview

This project demonstrates the deployment and use of Wazuh as a Security Information and Event Management (SIEM) platform in a virtualized home lab environment.

The lab focuses on collecting Windows security events, detecting suspicious activity, investigating alerts, and analyzing security-related events through the Wazuh dashboard.

## Lab Environment

- Wazuh Server: Ubuntu Server 24.04 LTS
- Endpoint: Windows 11
- Wazuh Agent: `win11-vm`
- Virtualization: Oracle VirtualBox
- Network: NAT and Host-only networking

## Architecture

```text
Windows 11 Endpoint
        |
        v
Wazuh Agent
        |
        v
Wazuh Server
        |
        v
Security Event Collection
        |
        v
Detection Rules and Alerts
        |
        v
Threat Hunting and Investigation
```

## Detection Scenarios

### 1. Windows Failed Login

A failed Windows authentication attempt was simulated and investigated through Wazuh.

- Windows Event ID: `4625`
- Wazuh Rule ID: `60122`
- Rule Level: `5`
- Result: Authentication failure detected and investigated.

Evidence: [Failed Login](attack-simulations/failed-login/)

### 2. File Integrity Monitoring (FIM)

A monitored Windows test file was modified to verify that Wazuh detects file integrity changes.

- Monitored directory: `C:\Wazuh-Test`
- Windows test file: `C:\Wazuh-Test\test.txt`
- Wazuh Rule ID: `550`
- Rule Level: `7`
- Detection: `Integrity checksum changed`
- Result: File modification detected and investigated.

Evidence: [File Integrity Monitoring](attack-simulations/fim/)

### 3. PowerShell Activity Detection

PowerShell Script Block Logging was enabled, and the Windows PowerShell Operational event channel was monitored by Wazuh.

- Windows Event ID: `4104`
- Wazuh Rule ID observed: `91843`
- Rule Level: `3`
- Detection: PowerShell activity associated with registry modification.
- Result: PowerShell logging and Wazuh detection were investigated.

Evidence: [PowerShell Detection](attack-simulations/powershell/)

## Skills Demonstrated

- SIEM Deployment and Configuration
- Windows Security Event Monitoring
- Wazuh Agent Deployment
- Threat Hunting
- Alert Analysis and Investigation
- File Integrity Monitoring
- PowerShell Activity Monitoring
- Windows Event Log Analysis
- MITRE ATT&CK Mapping
- Virtualized Lab Networking

## Project Structure

```text
wazuh-soc-home--lab/
├── README.md
└── attack-simulations/
    ├── failed-login/
    ├── fim/
    └── powershell/
```

Each scenario folder contains documentation and supporting evidence.

## Disclaimer

This lab is intended for educational and defensive cybersecurity purposes. All simulations are performed in a controlled virtual environment.
