# Wazuh SOC Home Lab

A hands-on Wazuh SOC home lab focused on Windows security monitoring, threat detection, log analysis, and incident investigation.

## Project Overview

This project demonstrates the deployment and use of Wazuh as a Security Information and Event Management (SIEM) platform in a virtualized home lab environment.

The lab focuses on collecting Windows security events, detecting suspicious activity, analyzing alerts, and investigating security incidents.

## Lab Environment

Wazuh Server:
Ubuntu Server 24.04 LTS

Endpoint:
Windows 11

Wazuh Agent:
win11-vm

Virtualization:
Oracle VirtualBox

Network:
Host-only network

## Architecture

Windows 11 Endpoint
        |
        | Wazuh Agent
        v
Wazuh Server
        |
        v
Security Events
        |
        v
Detection and Alerts
        |
        v
Investigation

## Detection Scenarios

1. Windows Failed Login

A failed Windows authentication attempt was simulated and detected by Wazuh.

Windows Security Event ID:
4625

Wazuh Rule:
60122

The event was investigated through the Wazuh Threat Hunting interface.

## Skills Demonstrated

Windows Security Monitoring

SIEM and Log Analysis

Security Event Investigation

Threat Detection

Wazuh Agent Deployment

Windows Event Logs

MITRE ATT&CK Mapping

Incident Investigation

## Project Structure

attack-simulations/
    failed-login/
        README.md
        detection and investigation screenshots

## Future Scenarios

File Integrity Monitoring

PowerShell Activity Detection

Multiple Failed Login Detection

Suspicious Process Detection

Custom Wazuh Detection Rules

MITRE ATT&CK Based Investigations
