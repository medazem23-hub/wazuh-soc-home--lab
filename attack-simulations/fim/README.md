Detection Scenario 02 – File Integrity Monitoring

Objective

Modify a monitored Windows file and verify that Wazuh detects the change using File Integrity Monitoring (FIM).

Environment

Wazuh Server: Ubuntu Server 24.04 LTS

Endpoint: Windows 11

Agent: win11-vm

Monitored Directory: C:\Wazuh-Test

Monitored File: C:\Wazuh-Test\test.txt

Detection

The file test.txt was initially created with the content:

Initial content

The file was then modified to:

Modified content

Wazuh detected the modification through its FIM mechanism.

Detection Details

Rule ID: 550

Rule Level: 7

Event: Integrity checksum changed

Mode: realtime

Changed attributes included:

size

mtime

md5

sha1

Investigation

The event was investigated through Wazuh Threat Hunting.

The raw JSON event showed changes in file metadata and integrity values, including:

size_before: 17

size_after: 18

mtime_before: 2026-09-26T16:37:50.000Z

mtime_after: 2026-09-26T16:53:44.000Z

MD5 and SHA-256 values were also recorded by Wazuh.

Result

The modification of a monitored Windows file was successfully detected and investigated using Wazuh File Integrity Monitoring.

Detection Flow

File Modified
↓
Wazuh FIM
↓
Wazuh Agent
↓
Wazuh Manager
↓
Rule 550
↓
Alert
↓
Investigation

Evidence

40-fim-file-modified.png

41-fim-json-details.png
