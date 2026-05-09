# 🎣 Phishing Simulation & Analysis

## Overview
Two-part project: analyzing real phishing samples for IOCs, and simulating a phishing campaign to test security awareness.

## Part 1 — Phishing Sample Analysis

### Samples Analyzed: 10+
Each sample was processed through:
- Manual email header analysis
- URL reputation checks (VirusTotal)
- Domain WHOIS lookups
- IP geolocation and ASN analysis
- MITRE ATT&CK TTP mapping

### IOCs Extracted (examples — sanitized)
| Type | Indicator | Threat |
|---|---|---|
| URL | hxxp://login-secure[.]verify-account[.]com | Credential harvesting |
| IP | 185.220.xxx.xxx | Known Tor exit node |
| Domain | paypa1[.]support-update[.]net | Typosquatting |
| Sender | support@micros0ft[.]helpdesk[.]ru | Brand impersonation |

## Part 2 — Phishing Simulation (Mastercard Exercise)

- Designed realistic phishing email mimicking internal IT communications
- Simulated against 6 departments
- Identified 2 high-risk departments (>40% click rate)
- Produced a 5-slide security awareness training presentation

## Key Files
- `email-samples/` — Sanitized phishing samples for analysis
- `ioc-analysis/` — Extracted indicators and VirusTotal reports

## Report
📄 [View Full Phishing Threat Report →](../Reports/Phishing-Threat-Report.md)
