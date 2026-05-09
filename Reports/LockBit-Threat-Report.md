# 🦠 LockBit Ransomware — Threat Intelligence Report

**Date:** 2026 | **Author:** Ajay Kalbhile | **Framework:** MITRE ATT&CK

---

## Executive Summary

LockBit is one of the most prolific ransomware-as-a-service (RaaS) operations in history, responsible for thousands of attacks globally. This report covers its attack lifecycle, TTPs, known IOCs, and defensive recommendations.

---

## Threat Actor Profile

| Attribute | Detail |
|---|---|
| Group Name | LockBit (LockBit 2.0 / LockBit 3.0 / LockBit Black) |
| Type | Ransomware-as-a-Service (RaaS) |
| Active Since | 2019 |
| Primary Targets | Healthcare, Finance, Critical Infrastructure |
| Ransom Demand Range | $50,000 – $50,000,000+ |

---

## Attack Lifecycle (MITRE ATT&CK Mapping)

| Phase | Technique | ATT&CK ID |
|---|---|---|
| Initial Access | Phishing, RDP brute force, VPN exploits | T1566, T1110, T1190 |
| Execution | PowerShell, WMI | T1059.001, T1047 |
| Persistence | Registry run keys, Scheduled tasks | T1547.001, T1053 |
| Privilege Escalation | UAC bypass, token impersonation | T1548, T1134 |
| Defense Evasion | Disable AV/EDR, log clearing | T1562, T1070 |
| Lateral Movement | SMB, PsExec, RDP | T1021 |
| Exfiltration | StealBit custom tool | T1041 |
| Impact | File encryption, double extortion | T1486, T1657 |

---

## Known IOCs (Sanitized Examples)

```
File Hashes (SHA-256):
- LockBit 3.0: 0d[...]e2f (example format — do not use as current intel)

Mutex Names:
- {BEF0A259-53C3-47F5-9E6E-56A38D2F5A10}

File Extensions:
- .lockbit, .abcd, [random 9-char extension]

Ransom Note Name:
- Restore-My-Files.txt

Registry Key:
- HKCU\SOFTWARE\[victim_id]
```

---

## Defensive Recommendations

1. **Patch RDP and VPN** — Most LockBit initial access is through known CVEs
2. **MFA everywhere** — Especially on remote access and admin accounts
3. **Offline backups** — LockBit specifically targets and encrypts network-connected backups
4. **Disable SMBv1** — Used heavily for lateral movement
5. **EDR with behavioral detection** — Signature-based AV misses LockBit variants
6. **Network segmentation** — Limits lateral movement blast radius
7. **Monitor for LOLBin abuse** — PowerShell, WMI, PsExec used in every LockBit campaign

---

## References

- CISA Advisory AA23-075A
- NCA / Europol LockBit disruption operation (Feb 2024)
- MITRE ATT&CK Group G0075

---

*This report is for educational and defensive purposes only.*
