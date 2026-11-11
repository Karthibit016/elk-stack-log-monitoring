# ELK Stack – Application Log Monitoring

## Project Overview

Implemented a local centralized log monitoring system using the ELK Stack (Elasticsearch, Logstash and Kibana) with Filebeat for log collection.

The project demonstrates how application logs can be collected, processed, stored, searched and visualized using open-source monitoring tools.

## Architecture

Application Log File → Filebeat → Logstash → Elasticsearch → Kibana

## Technologies Used

- **Elasticsearch 9.5.6** – Stores and indexes application logs.
- **Logstash 9.5.6** – Processes and transforms log events.
- **Kibana 9.5.6** – Provides log visualization and dashboards.
- **Filebeat 9.5.6** – Collects and forwards application logs.
- **Ubuntu 24.04 LTS (WSL2)** – Local development environment.

## Implementation

### 1. Elasticsearch
- Installed and configured Elasticsearch.
- Enabled authentication and HTTPS.
- Verified Elasticsearch using its REST API.

### 2. Kibana
- Installed and connected Kibana to Elasticsearch.
- Created an index data view named `Application Logs`.
- Used Discover to inspect indexed application logs.

### 3. Logstash
- Configured a Beats input on port `5044`.
- Used Grok to extract timestamps, log levels and messages.
- Used the Date filter to process event timestamps.
- Configured Elasticsearch output to store processed events.

### 4. Filebeat
- Configured a Filestream input to monitor application log files.
- Configured Logstash as the output destination.
- Enabled and started the Filebeat systemd service.

## Sample Log Data

```text
2026-11-10 10:00:00 INFO Application started successfully
2026-11-10 10:01:00 WARN High memory usage detected
2026-11-10 10:02:00 ERROR Database connection failed
2026-11-10 10:03:00 INFO Database connection restored
2026-11-10 10:04:00 ERROR API request failed with status 500
```

## Kibana Dashboard

Created an application monitoring dashboard containing:

- Log Count by Severity
- Total Log Count
- Total Error Logs
- Total Warning Logs
- Log Activity Over Time

## Verification

Successfully tested the complete Filebeat-to-Logstash connection and verified that application log events were indexed in Elasticsearch.

## Key Learning Outcomes

- ELK Stack installation and configuration.
- Centralized application log management.
- Log collection using Filebeat.
- Log parsing and transformation using Logstash.
- Elasticsearch indexing and REST API queries.
- Kibana data views, Discover and dashboard creation.
- Linux service management and troubleshooting.

## Environment

- OS: Ubuntu 24.04 LTS on WSL2
- Stack version: 9.5.6
- Deployment: Local development environment

## Future Improvements

- Monitor logs from multiple application servers.
- Configure alerting for ERROR-level events.
- Create additional dashboards and visualizations.
- Deploy the ELK Stack on AWS.
- Implement secure communication between Filebeat and Logstash.

---

**Author:** Karthik Sudharsan M

**GitHub:** https://github.com/Karthibit016
