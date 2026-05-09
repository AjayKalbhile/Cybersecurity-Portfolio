# ☁️ Cloud Security — Securing AWS S3 Buckets

## Overview
Hands-on exploration of S3 misconfiguration vulnerabilities and remediation on AWS Free Tier.

## Vulnerabilities Tested

| Misconfiguration | Risk Level | Fixed |
|---|---|---|
| Public "Block Public Access" disabled | Critical | ✅ |
| Bucket ACL set to public-read | High | ✅ |
| No server-side encryption (SSE) | Medium | ✅ |
| No access logging enabled | Medium | ✅ |
| No bucket versioning | Low | ✅ |
| Overly permissive IAM bucket policy | High | ✅ |

## Remediation Steps Applied
1. Enabled "Block all public access" at account level
2. Replaced ACL-based access with IAM policy-based access
3. Enabled SSE-S3 encryption by default
4. Enabled S3 access logging to a separate audit bucket
5. Enabled versioning for critical buckets
6. Applied least-privilege IAM policy (deny * by default)

## Key Files
- `aws-configs/` — Example bucket policies and IAM policies (sanitized)

## Lessons Learned
The most dangerous S3 mistakes aren't complex. They're defaults that should have been changed on setup. Most real-world S3 breaches (Capital One, Twitch) trace back to IAM overpermission — not sophisticated exploits.
