 🔒 Web Portal Authentication Audit & Hardening Lab

This repository hosts a personal cybersecurity project focused on simulating web application attacks and deploying edge firewall protections. The application is deployed live via GitHub Pages over an encrypted HTTPS connection.

---

 🚀 Project Overview
- **Target Sub-Path:** `/my-secure-login/`
- **Platform Environment:** Kali Linux CLI & Virtualized Lab environment
- **Objective:** Map network surface, perform header security audits, and implement edge mitigation.

---

 🔍 Phase 1: Automated Vulnerability Reconnaissance (Nmap & Nikto)
Using network discovery tools inside Kali Linux, I scanned the infrastructure deployment to map open ports and audit deployment headers.

 Nmap Port Mapping
Confirmed that port `80` (HTTP) and port `443` (HTTPS) are active and open.
![Nmap Scan](<img width="1599" height="430" alt="WhatsApp Image 2026-10-07 at 16 09 21" src="https://github.com/user-attachments/assets/85760246-2a81-4645-8a6c-b22645c71669" />


### Nikto Header Audit
Identified three critical security misconfigurations (Missing X-Frame-Options, HSTS, and X-Content-Type-Options).
![Nikto Scan]<img width="1600" height="789" alt="WhatsApp Image 2026-10-07 at 16 10 54" src="https://github.com/user-attachments/assets/f24a6431-ec9d-49ab-bf5f-861a06b9c922" />


---

 🦈 Phase 2: Credentials Interception Simulation
To analyze cleartext transport risks, I inspected the browser-side application layer during authentication.

 Initial Interface Deployment
![Login Interface]<img width="1280" height="800" alt="WhatsApp Image 2026-10-08 at 14 55 32" src="https://github.com/user-attachments/assets/e8225ea2-228d-4b29-92aa-d02cbafb1180" />


 JavaScript Alert Capture
Deployed a client-side DOM handler that captures inputs (`Username` and `Password`) in plaintext.
![JavaScript Plaintext Capture]<img width="1280" height="800" alt="WhatsApp Image 2026-10-08 at 14 55 41" src="https://github.com/user-attachments/assets/5e7343d6-1119-498d-994d-e642bf19a4bc" />


 Burp Suite Proxy Configuration
Established a local network loop using Burp Suite Proxy (Intercept is ON) inside Kali Linux to trap outbound authentication payloads.
![Burp Suite Intercept]<img width="1280" height="800" alt="WhatsApp Image 2026-10-08 at 14 56 05" src="https://github.com/user-attachments/assets/3250a23b-d77e-4a00-807e-a4aff2fcff54" />


---

 🧱 Phase 3: Blue Team Remediation (Cloudflare Edge WAF)
To shield the infrastructure from the automated scanner threats discovered during the Nikto scan, the domain traffic was routed into Cloudflare edge infrastructure.

- **Custom WAF Deployment:** Activated a target security rule named `Block Login Exploits`.
- **Action Implemented:** `Managed Challenge` (Enforces smart verification to block malicious bots and brute-force scripts).
![Cloudflare WAF Active]<img width="1912" height="831" alt="Capture d&#39;écran 2026-10-06 180526" src="https://github.com/user-attachments/assets/41dc789c-0f0a-43cc-a973-3c41e0dee824" />


---

## 🏆 Portfolio Links
All live metrics, screenshots, and technical details are documented inside my official web portfolio:
👉 **[Check My Cyber Labs Page]([https://google.com](https://sites.google.com/view/ismailfendou-cybersec/my-cyber-labs))**
