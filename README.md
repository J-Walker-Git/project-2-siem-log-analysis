# SIEM Log Analysis Lab

This project demonstrates a beginner-friendly SOC lab built with Microsoft Sentinel, Azure Arc, and a Windows 11 virtual machine in VMware Workstation. It focuses on the core operational flow of a SOC analyst: onboarding an endpoint, validating telemetry, querying security logs, and investigating failed authentication activity.

## Summary

I built a small SIEM lab to practice Windows event log collection, data connector setup, KQL investigation, and basic detection validation. The lab shows the full path from onboarding a VM into Azure to confirming log ingestion and running queries in Sentinel.

## Objectives

- Onboard a Windows 11 VM to Azure Arc.
- Configure Microsoft Sentinel for log analysis.
- Create and validate a Windows Security Events data collection rule.
- Confirm SecurityEvent ingestion in Log Analytics.
- Investigate failed logons with KQL.

## Lab Stack

- VMware Workstation
- Windows 11 x64 VM
- Azure Arc
- Microsoft Sentinel
- Log Analytics Workspace
- Azure Monitor Agent
- Windows Security Events
- Microsoft Defender for Cloud

## Evidence Sequence

1. Azure Arc connected ![image alt](https://github.com/J-Walker-Git/siem-log-analysis/blob/800343df68813afc8b2e8de93a8765396c973ba8/01-azure-arc-connected.png)

2.Azure Arc onboarding script ![image alt](https://github.com/J-Walker-Git/siem-log-analysis/blob/d50da997836e808c0a7955c3474da22512e1b8be/02-onboarding-script.png)

3. Windows Security Events via AMA connector ![image alt](https://github.com/J-Walker-Git/siem-log-analysis/blob/01adab6bed264583f59c79773f1fd8e60cb291fb/03-sentinel-data-connector.png)

4. SecurityEvent query results ![image alt](https://github.com/J-Walker-Git/siem-log-analysis/blob/2eb0d09712262b5e98526aba34cf0d8766566d7a/04-logs-query-event-data-1.png)

5. Failed logon investigation ![image alt](https://github.com/J-Walker-Git/siem-log-analysis/blob/8860d78a6140f65db6fae861c4417967696a0398/05-unsuccessful-logons-due-to-incorrect-password.png)

## Key Skills Demonstrated

- Cloud onboarding and endpoint integration.
- SIEM configuration and validation.
- KQL querying.
- Security event triage.
- Technical documentation.
