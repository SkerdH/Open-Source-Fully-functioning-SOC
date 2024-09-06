# Building a Open-Source Fully Functioning SOC

## Introduction

This project demonstrates how to build a secure, scalable, and intelligent Security Information and Event Management (SIEM) system using open-source tools. By leveraging free software, organizations can minimize costs while maintaining robust security comparable to commercial solutions.

## Key Components of the SIEM Stack

### 1. Log Ingestion

Collect logs from various sources:

- **Endpoints** (e.g., Windows Events, Sysmon, PowerShell)
- **Network Devices** (e.g., firewalls, IDS/IPS)
- **Cloud Logs** (e.g., AWS CloudTrail, O365)

**Tool**: [Graylog](https://www.graylog.org/)  
**Enterprise Alternatives**: Splunk, LogRhythm, IBM QRadar

### 2. Log Analysis

Analyze collected logs to prioritize events and detect threats.

**Tool**: [Wazuh](https://wazuh.com/)  
**Enterprise Alternatives**: AlienVault USM, McAfee ESM, Sumo Logic

### 3. Backend Storage

Store logs efficiently with scalability and high availability.

**Tool**: Wazuh-Indexer (Fork of OpenSearch)  
**Enterprise Alternatives**: Elasticsearch, Azure Monitor Logs, Google Chronicle

### 4. Visualization

Create customizable dashboards for effective monitoring.

**Tool**: [Grafana](https://grafana.com/)  
**Enterprise Alternatives**: Kibana, Tableau, Power BI

### 5. Intelligence Enrichment

Enrich logs with threat intelligence feeds for better threat detection.

**Tools**: [OpenCTI](https://www.opencti.io/), [MISP](https://www.misp-project.org/)  
**Enterprise Alternatives**: Recorded Future, ThreatConnect, Palo Alto AutoFocus

### 6. Case Management

Collaborate on incidents and manage response tasks effectively.

**Tools**: [TheHIVE](https://thehive-project.org/) / [Cortex](https://www.cortex-app.com/)  
**Enterprise Alternatives**: ServiceNow, IBM Resilient, Splunk Phantom

### 7. Automation

Automate routine tasks to improve response times.

**Tool**: [Shuffle](https://shuffler.io/)  
**Enterprise Alternatives**: Cortex XSOAR, Rapid7 InsightConnect, Swimlane

### 8. Investigation

Perform digital forensics and incident response quickly across endpoints.

**Tool**: [Velociraptor](https://www.velocidex.com/velociraptor/)  
**Enterprise Alternatives**: Carbon Black Response, CrowdStrike Falcon, FireEye Endpoint Security

### 9. Health Monitoring

Monitor the performance and uptime of the SIEM stack.

**Tools**: [InfluxDB](https://www.influxdata.com/) / [Telegraf](https://github.com/influxdata/telegraf), [Uptime Kuma](https://github.com/louislam/uptime-kuma)  
**Enterprise Alternatives**: Datadog, SolarWinds, Zabbix

## Deployment Overview

The stack includes the following open-source tools:

- **Wazuh-Indexer** (OpenSearch)
- **Graylog**
- **Wazuh Manager / Agents**
- **Grafana**
- **MISP**
- **OpenCTI**
- **TheHIVE / Cortex**
- **Velociraptor / Agents**
- **Shuffle**
- **InfluxDB / Telegraf**
- **Uptime Kuma**

## How to Get Started

1. Set up backend storage with Wazuh-Indexer.
2. Install Graylog and connect it to your log sources.
3. Deploy Wazuh Manager to analyze logs and enrich data with threat intelligence from OpenCTI and MISP.
4. Set up Grafana to create customizable dashboards for real-time monitoring.
5. Automate workflows using Shuffle.
6. Use Velociraptor to perform forensic analysis across endpoints.
7. Monitor the stack’s health with InfluxDB/Telegraf and Uptime Kuma.

## Conclusion

This open-source SIEM stack offers a cost-effective and customizable solution for building a secure, intelligent, and scalable Security Operations Center (SOC). By leveraging these tools, organizations can achieve commercial-grade security while maintaining flexibility and control over their environment.

