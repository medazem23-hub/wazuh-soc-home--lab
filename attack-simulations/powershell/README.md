Detection Scenario 03 – PowerShell Activity Detection

Objective

Monitor Windows PowerShell activity with Wazuh and detect suspicious PowerShell behavior.

Environment

- Wazuh Server: Ubuntu Server 24.04 LTS
- Endpoint: Windows 11
- Agent: win11-vm
- Wazuh Rule: 91843
- Windows Event ID: 4104
- Event Channel: Microsoft-Windows-PowerShell/Operational

Configuration

PowerShell Script Block Logging was enabled on the Windows endpoint.

Wazuh was configured to monitor the PowerShell Operational event channel:

<localfile>
  <location>Microsoft-Windows-PowerShell/Operational</location>
  <log_format>eventchannel</log_format>
</localfile>

Detection

A PowerShell command was executed on the Windows endpoint.

Windows generated Event ID 4104:

Creating Scriptblock text

The event was collected by the Wazuh Agent and processed by the Wazuh Manager.

Wazuh detected PowerShell activity using Rule 91843.

Rule Details

Rule ID: 91843

Rule Level: 3

Groups:

- windows
- powershell

Rule Description:

Powershell executed "New-ItemProperty -Path". Possible addition of new item to registry

MITRE Techniques:

- PowerShell
- Modify Registry

MITRE Tactics:

- Execution
- Defense Evasion

Investigation

The event was investigated through Wazuh Threat Hunting.

The Windows PowerShell Operational channel generated Event ID 4104, which contains the PowerShell Script Block text.

Wazuh then applied its PowerShell detection rules and generated an alert for the observed PowerShell activity.

Detection Flow

PowerShell Activity
↓
Script Block Logging
↓
Windows Event ID 4104
↓
Microsoft-Windows-PowerShell/Operational
↓
Wazuh Agent
↓
Wazuh Manager
↓
Rule 91843
↓
Alert
↓
Investigation

Evidence

42-powershell-rule.png

43-powershell-event-4104.png

Result

PowerShell activity was successfully logged by Windows, collected by the Wazuh Agent, processed by the Wazuh Manager, and detected using Wazuh PowerShell detection rules.
