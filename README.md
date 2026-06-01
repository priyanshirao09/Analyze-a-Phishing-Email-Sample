# Phishing Email Analysis

## Overview

This document is a step-by-step analysis of a real-world phishing email that impersonates **PayPal**. It serves as a practical cybersecurity exercise for identifying common phishing tactics, attack vectors, and social engineering techniques.

**Tools Required:** Email client or saved email file (text), free online header analyzer

---

## Analysis Steps

### 1. Obtain a Sample Phishing Email
A realistic phishing email is provided as the subject of analysis. It mimics an official PayPal security alert, warning the recipient of account limitations and demanding immediate action.

### 2. Examine the Sender's Address for Spoofing
The sender uses `paypa1.com` — a typosquatted domain where the letter `l` is replaced with the digit `1`. The Reply-To address points to a completely different fake domain (`paypal-secure-login.net`), which is a strong spoofing indicator.

### 3. Check Email Headers for Discrepancies
Key header anomalies identified:
- Email originated from a Russian bulk-mail server (`bulk-mail-host.ru`) unrelated to PayPal
- Sent via **PHPMailer 6.1**, a tool commonly used in mass phishing campaigns
- Message-ID domain matches the phishing server, not PayPal's infrastructure

### 4. Identify Suspicious Links or Attachments
The email contains a malicious URL: `paypal-secure-verify-account.xyz/login?token=xR77QpL`
- The `.xyz` TLD is cheap and commonly used in phishing sites
- The `?token=` parameter uniquely tracks which victims clicked the link
- Leads to a fake login page designed to steal credentials

### 5. Look for Urgent or Threatening Language
Multiple high-pressure phrases are used to override rational judgment:
- *"URGENT: Your PayPal Account Has Been Limited"*
- *"verify your information IMMEDIATELY"*
- *"permanently suspended within 24 hours"*

### 6. Note Mismatched URLs
The link text appears legitimate, but the actual destination is a fraudulent domain — a technique known as **URL masking**. Hovering over the link (without clicking) would reveal the true malicious URL.

### 7. Verify Spelling and Grammar Errors
Multiple basic errors were found:
- *"bellow"* instead of *"below"*
- *"loose access"* instead of *"lose access"*
- *"contact are support team"* instead of *"our support team"*

### 8. Summarize Phishing Traits
A complete list of all phishing indicators found is compiled as a summary.

---

## Phishing Indicators Found

| # | Indicator | Detail |
|---|---|---|
| 1 | Typosquatted sender domain | `paypa1.com` (digit `1` instead of letter `l`) |
| 2 | Fake Reply-To domain | `paypal-secure-login.net` |
| 3 | Suspicious origin server | `bulk-mail-host.ru` (Russian bulk-mail host) |
| 4 | Mass phishing tool | PHPMailer 6.1 |
| 5 | Malicious URL | `paypal-secure-verify-account.xyz` |
| 6 | Victim-tracking token | `?token=xR77QpL` in the URL |
| 7 | URL masking | Displayed link hides the real destination |
| 8 | Social engineering | Fake urgency and 24-hour account suspension threat |
| 9 | Grammar/spelling errors | "bellow", "loose access", "contact are support" |

**Verdict:** Confirmed phishing attempt with high confidence. Objective is credential theft via a fake PayPal login page.

---

## Use Cases

- Cybersecurity awareness and employee training
- SOC analyst onboarding exercises
- Academic coursework on email security and social engineering
- Self-study for identifying phishing in everyday email

---

## What To Do If You Receive This Email

1. Do **not** click any links
2. Do **not** enter credentials on any linked page
3. Report it as phishing in your email client
4. Forward to `spoof@paypal.com` (PayPal's official abuse address)
5. Delete the email immediately

---

> **Disclaimer:** The phishing email sample in this document is strictly for educational purposes. Do not visit any of the URLs referenced.
