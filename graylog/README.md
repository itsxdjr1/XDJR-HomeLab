# Graylog SIEM

## Overview
I deployed Graylog as a centralized SIEM for my homelab to collect and monitor logs from Windows endpoints, Proxmox, and my MikroTik router.

Again, this isn't very practical for my homelab as it's private, but for learning it was amazing!

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

<img width="1760" height="894" alt="image" src="https://github.com/user-attachments/assets/bda462cf-896f-4b47-8d2d-a6a4fa55c290" />

## What I Learned
- Windows Event IDs and logon types
- Graylog pipelines and streams
- Winlogbeat / Sidecar configuration
- Alert tuning (very annoying)
- Troubleshooting duplicate events
- Centralized logging architecture
