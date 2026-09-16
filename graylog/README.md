# Graylog SIEM

## Overview
I deployed Graylog as a centralized SIEM for my homelab to collect and monitor logs from Windows endpoints, Proxmox, and my MikroTik router.

## Architecture
- Windows 10/11 → Graylog Sidecar + Winlogbeat
- MikroTik → Syslog
- Proxmox → Syslog
- Graylog → Streams, searches, alerts, and dashboards

## What I Built
- Centralized Windows Event Log collection
- Windows authentication monitoring
- Successful and failed logon detections
- Custom streams
- Alerts
- Dashboard views
- MikroTik and Proxmox log ingestion

## Screenshots

<img width="3822" height="1940" alt="image" src="https://github.com/user-attachments/assets/41140062-e877-4bbe-8de4-68771a600191" />


## What I Learned
- Windows Event IDs and logon types
- Graylog pipelines and streams
- Winlogbeat / Sidecar configuration
- Alert tuning
- Troubleshooting duplicate events
- Centralized logging architecture
