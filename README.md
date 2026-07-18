# FUTURE_CS_01 - Vulnerability Assessment Report

## Overview

This repository documents my work for the Future Interns Cyber Security Task 1: **Vulnerability Assessment Report**.

The objective of this task was to perform a passive vulnerability assessment of a publicly accessible web application and document identified security weaknesses, associated risks, and remediation recommendations in a professional report format.

This assessment followed a read-only and ethical approach. No exploitation, brute-force testing, denial-of-service testing, authentication bypass, or harmful activity was performed.

---

## Target Website

**Website:** Acublog / ASP.NET VulnWeb Test Site  
**URL:** http://testaspnet.vulnweb.com/  
**Assessment Type:** Passive Vulnerability Assessment/Read-Only Review

---

## Scope

The assessment was limited to publicly accessible resources and non-intrusive testing techniques.

### What was allowed:

- Public webpage analysis
- HTTP response header inspection
- Cookie analysis
- Login form observation
- Passive vulnerability scanning
- Basic network service discovery
- Configuration review

### What was restricted:

- Vulnerability Exploitation 
- Brute-force attacks
- Authentication bypass
- Denial of Service (DoS)
- Data modification
- Unauthorised access attempts
- Active vulnerability scanning
- Penetration testing

---

## Tools 

- Chrome Developer Tools
- OWASP ZAP Passive Scan
- Nmap on Kali
- Canva for report design
- GitHub for documentation

---

## Methodology

The assessment was performed using a passive and non-destructive approach.

1. Reviewed the target website through publicly accessible pages.
2. Inspected HTTP response headers using Chrome Developer Tools.
3. Reviewed visible login form behavior without submitting malicious input.
4. Checked session cookie attributes using Chrome Developer Tools.
5. Used OWASP ZAP in passive scan mode to identify non-intrusive alerts.
6. Used Nmap for basic port and exposure analysis only.
7. Documented findings with risk classification and remediation guidance.

---

## Key Vulnerable Findings

| No. | Finding | Risk | Source |
|---|---|---|---|
| 1 | Website Uses HTTP Instead of HTTPS | High | Browser Developer Tools / Nmap |
| 2 | Login Form Served Over HTTP | High | Browser Developer Tools |
| 3 | Missing Common Security Headers | Medium | Browser Developer Tools / OWASP ZAP |
| 4 | Absence of Anti-CSRF Tokens | Medium | OWASP ZAP Passive Scan |
| 5 | Weak Cookie Security Attributes | Medium | Browser Developer Tools |
| 6 | Backend Technology and Version Disclosure | Low / Medium | Browser Developer Tools / OWASP ZAP |
| 7 | User Controllable HTML Element Attribute / Potential XSS Observation | Informational | OWASP ZAP Passive Scan |
| 8 | Charset Mismatch | Informational | OWASP ZAP Passive Scan |

---

## Positive Security Observations

- Only one public service was identified by the basic Nmap scan.
- Nmap reported `80/tcp open http`, while other scanned TCP ports were filtered.
- Public `robots.txt` did not reveal sensitive or restricted paths.
- `sitemap.xml` was not publicly available and did not disclose additional paths.

