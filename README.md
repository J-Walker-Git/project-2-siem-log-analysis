# SIEM Log Analysis Lab

This project demonstrates a beginner-friendly SOC lab built with Microsoft Sentinel, Azure Arc, and a Windows 11 virtual machine in VMware Workstation Pro. It demonstrates onboarding an endpoint, validating telemetry, querying security logs, and investigating failed authentication activity.

## Summary

This lab was built to practice Windows event log collection, data connector setup, KQL investigation, and basic detection validation. The project shows the full path from onboarding a VM into Azure to confirming log ingestion and running queries in Sentinel.

## Objectives

- Onboard a Windows 11 VM to Azure Arc.
- Configure Microsoft Sentinel for log analysis.
- Create and validate a Windows Security Events data collection rule.
- Confirm SecurityEvent ingestion in Log Analytics.
- Investigate failed logons with KQL.

## Lab Stack

- VMware Workstation Pro
- Windows 11 x64 VM
- Azure Arc
- Microsoft Sentinel
- Log Analytics Workspace
- Azure Monitor Agent
- Windows Security Events

## Evidence Sequence


**1.** **Azure Arc connected** ![image alt](https://github.com/J-Walker-Git/siem-log-analysis/blob/bd7559d8eed73980cb6fb62b6714df4bf29c2d74/setup/01-azure-arc-connected.png)

**2.**  **Azure Arc onboarding script** ![image alt](https://github.com/J-Walker-Git/siem-log-analysis/blob/eb86280524957721ca0512e3a8180e65f4e601a4/setup/01-onboarding-script.png)

**3.** **Windows Security Events via AMA connector** ![image alt](https://github.com/J-Walker-Git/siem-log-analysis/blob/34c4c0a9f733b4d9607f0dc52cd6b5485a91c1b4/setup/02-sentinel-data-connector.png)

**4.** **SecurityEvent query results** ![image alt](https://github.com/J-Walker-Git/siem-log-analysis/blob/4eee1004d7d79f4564c5871ecd54fca63fb74e7d/setup/logs-query-event-data-1.png)

**5.** **Failed logon investigation** ![image alt](https://github.com/J-Walker-Git/siem-log-analysis/blob/9d15395df47db83d9dbec7f4c7c646556802afb3/setup/unsuccessful-logons.png)


## KQL

Kusto Query Language is a tool used to explore data by identifying patterns, anomalies and outliers.
The language is easier to read and communicates intent more directly compared to structured query language (SQL)

**KQL example**
SecurityEvent
| where Computer contains "SOC-WIN11"
| sort by TimeGenerated desc
| take 50

**SQL example**
SELECT TOP 50 *
FROM SecurityEvent
WHERE Computer LIKE '%SOC-WIN11%'
ORDER BY TimeGenerated DESC;

![image alt](https://github.com/J-Walker-Git/siem-log-analysis/blob/f4e251b43ee40539de477c0f24e8e791e2f139ca/setup/05-sentinel-security-event-query-results-.png)


## Key Skills Demonstrated

- Cloud onboarding and endpoint integration.
- SIEM configuration and validation.
- KQL querying.
- Security event triage.
- Technical documentation.


## Notes

This is a beginner lab project but reflects real SOC fundamentals:
- Asset onboarding
- Log collection
- Event validation

## Future Improvements

I can build on what I have demonstrated here by:

- Increasing the attack activity for deeper investigation
- Adding basic threat hunting
- Adding more KQL threat hunting queries
- Creating analytics rules for repeated failed logons
- Collecting Defender alerts in Sentinel
