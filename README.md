Open-Source SOC with Wazuh, Graylog, and Security Tools
This project sets up a fully functional open-source SOC (Security Operations Center) utilizing Wazuh, Graylog, OpenSearch, and supporting tools like OpenCTI, MISP, and Velociraptor for security intelligence enrichment and incident response.

Architecture Overview
The SOC consists of the following components:

Wazuh: Central log collection and analysis tool for security monitoring.
Graylog: Used for log ingestion and further log analysis.
Wazuh Indexer: Backend storage (Elasticsearch-based) for log storage.
Grafana & Kibana: Visualization tools for monitoring and dashboards.
OpenCTI & MISP: Intelligence enrichment tools to gather threat intelligence.
TheHive & Cortex: Case management system for incident response.
Velociraptor: Investigative tool for forensic analysis.
The diagram shows the architecture after full deployment, with components spread across nodes, and demonstrates how log data flows from the Next-Generation Firewall (NGFW) into the system for analysis and monitoring.


Components
1. Wazuh
Centralized security monitoring, log collection, and analysis.
2. Graylog
Log management and analysis.
3. Wazuh Indexer (OpenSearch)
Elasticsearch-based backend storage to store and index logs.
4. Grafana & Kibana
Provides dashboards for visualizing logs and metrics from security events.
5. OpenCTI & MISP
Intelligence enrichment tools to bring threat intelligence data into the environment.
6. TheHive & Cortex
Case management system for managing incidents and response actions.
7. Velociraptor
Forensic investigation and incident response.
