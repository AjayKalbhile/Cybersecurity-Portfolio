# 🖥️ SOC Lab — Detecting Brute Force Attacks

## Overview
Home SIEM lab built with Splunk, monitoring 500+ log events/day from simulated Windows and Linux endpoints.

## Environment Setup
- **SIEM:** Splunk (Free tier)
- **Attack Source:** Kali Linux
- **Target:** DVWA (Damn Vulnerable Web App)
- **Monitoring:** Wazuh agent on endpoints

## What I Detected
| Attack Type | Detection Method | Alert Configured |
|---|---|---|
| SSH Brute Force | Failed login threshold >5 in 60s | ✅ Yes |
| RDP Brute Force | EventID 4625 correlation | ✅ Yes |
| Web Login Brute Force | HTTP 401 spike detection | ✅ Yes |

## Key Files
- `splunk-config/` — Exported alert rules and saved searches
- `screenshots/` — Evidence of detections and dashboard views

## Report
📄 [View Full SOC Lab Summary Report →](../Reports/SOC-Summary.md)
