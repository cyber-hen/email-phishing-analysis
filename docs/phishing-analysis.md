# 🧪 Email Phishing Analysis – Setup Guide

This guide documents the process of analyzing a phishing email impersonating Microsoft. It includes how the email was obtained, the step-by-step breakdown of its components, screenshots of each stage, and final recommendations for defense.

---

## 📥 How the Phishing Email Was Obtained

The phishing email was captured in a controlled SOC lab environment using a monitored inbox (`phishing@pot`). The email was flagged due to suspicious sender details and unusual content structure. It was preserved for forensic analysis and threat intelligence correlation.

---

## 🧠 Step-by-Step Analysis Process

### 1. **Header Inspection**
- **From**: `no-reply@access-accsecurity.com` (not a Microsoft domain)
- **Reply-To**: `solutionteamrecognizd02@gmail.com` (generic Gmail)
- **Return-Path**: `bounce@providentusezn.co.uk`
- **Sender IP**: `89.144.44.4` → Resolved to `providentusezn.co.uk`
- **SPF/DKIM/DMARC**: All failed or missing

### 2. **Email Content Review**
- Claims unusual sign-in from Russia (IP: `103.225.77.255`)
- Platform: Windows 10 | Browser: Firefox
- Urges user to “Report The User” via embedded links

### 3. **URL Analysis**
- Obfuscated and encoded URLs:
  - `http://thebandalisty.com/track/...` → Tracking pixel
  - `mailto:solutionteamrecognizd02@gmail.com` → Fake reporting/unsubscribe
- VirusTotal flagged the tracking URL as malicious (4/97 vendors)

### 4. **Threat Intelligence Lookup**
- Domains and IPs checked against threat databases
- `providentusezn.co.uk` and `thebandalisty.com` flagged for phishing/fraud

### 5. **Screenshots Captured**
- Email interface
- Fake login page
- VirusTotal and URLScan results
- Header breakdown and decoded URLs

---

## 🖼️ Screenshots of Each Stage

Stored in `screenshots/` folder:
- `email-interface.png`
- `fake-login-page.png`
- `virustotal-report.png`
- `header-analysis.png`

---

## ✅ Summary of Findings

- **Verdict**: Phishing attempt
- **Indicators**:
  - Inconsistent sender domains
  - Failed email authentication
  - Use of Gmail for replies and unsubscribe
  - Tracking pixel from suspicious domain
- **Risks**:
  - Credential theft
  - Data breach
  - Reputational damage

---

## 🛡️ Recommendations

- Mark email as spam/junk
- Do not click links or reply
- Never provide personal information via email
- Verify account activity directly via official Microsoft channels
- Report to internal security teams for awareness and response

---

> This analysis was conducted in a secure lab for educational and awareness purposes. All findings are documented to support phishing detection and SOC training.
