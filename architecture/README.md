# Lab Architecture

## Environment

- Wazuh Server: Ubuntu Server 24.04 LTS
- Endpoint: Windows 11
- Agent: `win11-vm`
- Virtualization: Oracle VirtualBox
- Networking: NAT and Host-only

## Architecture Diagram

```text
Windows 11 VM
192.168.56.105
      |
      | Wazuh Agent
      v
Host-only Network
      |
      v
Wazuh Server
192.168.56.106
      |
      v
Wazuh Manager
      |
      v
Security Alerts
      |
      v
Threat Hunting and Investigation
```

## Purpose

The Windows endpoint generates security events. The Wazuh Agent collects and forwards them to the Wazuh Server, where events are analyzed and alerts are generated.

The analyst uses the Wazuh Dashboard to investigate alerts and review security events.

## Network Isolation

The Host-only network allows communication between the Windows endpoint and Wazuh Server through a private virtual network.

The NAT adapter provides internet connectivity when needed.
