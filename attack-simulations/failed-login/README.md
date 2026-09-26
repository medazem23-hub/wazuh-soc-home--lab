Detection Scenario 01 – Windows Failed Login

Objective

Simulate a failed Windows login attempt and verify that Wazuh detects and investigates the resulting security event.

Environment

Wazuh Server: Ubuntu Server 24.04 LTS
Endpoint: Windows 11
Agent: win11-vm
Wazuh Rule: 60122
Windows Event ID: 4625

Detection

The failed login generated Windows Security Event ID 4625.

Wazuh detected the event using Rule 60122:

Logon Failure - Unknown user or bad password

Investigation

The event was investigated through Wazuh Threat Hunting.

Important findings:

Event ID: 4625
Rule ID: 60122
Rule Level: 5
Logon Type: 2
Authentication Package: Negotiate
Source IP: 127.0.0.1
Channel: Security

Result

The Windows authentication failure was successfully collected, detected, and investigated through the Wazuh SIEM.

Detection Flow

Windows Failed Login

↓

Windows Event ID 4625

↓

Wazuh Agent

↓

Wazuh Manager


Rule 60122

↓

Alert

↓

Investigation
