# Phishing Email Analysis — README

## Overview

This document presents a structured analysis of a real-world phishing email sample impersonating **PayPal**. It is designed as a hands-on cybersecurity exercise to help users identify common phishing tactics and indicators of compromise.

---

## Document Summary

**Title:** Analyze a Phishing Email Sample  
**Tools Required:** Email client or saved email file (text), free online header analyzer  
**Subject of Analysis:** A fake PayPal security alert email

---

## What's Inside

The document walks through a step-by-step analysis of a phishing email using the following methodology:

1. **Obtain a Sample Phishing Email** — A realistic phishing email is provided, impersonating PayPal with a spoofed sender, fake domain, and malicious link.

2. **Examine the Sender's Address** — Identifies the typosquatting technique used (`paypa1.com` instead of `paypal.com`) and the mismatched Reply-To domain.

3. **Check Email Headers for Discrepancies** — Analyzes header fields including the originating server (a Russian bulk-mail host), X-Mailer (PHPMailer), and Message-ID to detect illegitimate infrastructure.

4. **Identify Suspicious Links or Attachments** — Breaks down the malicious URL (`paypal-secure-verify-account.xyz`) and explains the victim-tracking token embedded in the link.

5. **Look for Urgent or Threatening Language** — Highlights social engineering tactics such as fake deadlines and account suspension threats.

6. **Note Mismatched URLs** — Explains URL masking, where a link appears legitimate but redirects to a fraudulent site.

7. **Verify Spelling and Grammar Errors** — Points out multiple errors ("bellow", "loose", "are support") as phishing red flags.

8. **Summarize Phishing Traits** — A comprehensive list of all phishing indicators found in the email.

---

## Key Findings

| Indicator | Detail |
|---|---|
| Spoofed sender domain | `paypa1.com` (digit `1` instead of letter `l`) |
| Fake Reply-To | `paypal-secure-login.net` |
| Origin server | `bulk-mail-host.ru` (Russia) |
| Email tool used | PHPMailer 6.1 (mass phishing script) |
| Malicious URL | `paypal-secure-verify-account.xyz` |
| Tracking token | `?token=xR77QpL` in the URL |
| Social engineering | Urgency, fear of account loss, fake 24-hour deadline |
| Grammar errors | "bellow", "loose access", "contact are support" |

**Conclusion:** This is a confirmed high-confidence phishing attempt aimed at stealing PayPal login credentials.

---

## Purpose & Use Cases

- Cybersecurity awareness training
- SOC analyst onboarding exercises
- Academic coursework on email security
- Personal education on recognizing phishing attacks

---

## Recommended Actions Upon Receiving Such Emails

- Do **not** click any links
- Do **not** enter credentials on linked pages
- Report the email as phishing to your email provider
- Forward to the impersonated company's abuse address (e.g., `spoof@paypal.com`)
- Delete the email immediately

---

## Disclaimer

The phishing email sample used in this document is for **educational purposes only**. The malicious URLs referenced should never be visited.
