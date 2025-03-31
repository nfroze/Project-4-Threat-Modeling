# **Risk Summary - Ransomware Attack on CareConnect360**

## **Risk Table**
| **Risk ID** | **Description** | **Severity** | **Likelihood** | **Impact** | **Controls Required** |
|------------|----------------|-------------|---------------|------------|----------------|
| R1 | Ransomware encrypts critical patient records, disrupting healthcare operations. | High | High | High | Secure Backups (Offline & Cloud), Business Continuity Plan (BCP), Endpoint Detection & Response (EDR) |
| R2 | Attackers use phishing to deliver ransomware via malicious attachments. | High | Medium | High | Email Scanning, Web Filtering, Security Awareness Training |
| R3 | Ransomware exploits unpatched software vulnerabilities to spread laterally. | High | Medium | High | Patch Management, Vulnerability Scanning, Network Segmentation |
| R4 | Attackers exfiltrate sensitive patient data before encryption (double extortion). | High | Medium | High | Data Loss Prevention (DLP), Network Segmentation, Encryption at Rest & In Transit |
| R5 | Insider threats intentionally deploy ransomware within CareConnect360 systems. | Medium | Low | High | Least Privilege Access, Insider Threat Monitoring, Privileged Access Management (PAM) |