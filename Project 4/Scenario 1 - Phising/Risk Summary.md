# **Risk Summary - Phishing Attack on CareConnect360**

## **Risk Table**
| **Risk ID** | **Description** | **Severity** | **Likelihood** | **Impact** | **Controls Required** |
|------------|----------------|-------------|---------------|------------|----------------|
| R1 | Employees fall victim to phishing emails, leading to credential theft. | High | High | High | Multi-Factor Authentication (MFA), Email Security (DMARC, SPF, DKIM), Security Awareness Training |
| R2 | Phishing links deliver malware, granting attackers remote access. | High | Medium | High | Endpoint Protection, Web Filtering, Email Scanning |
| R3 | Attackers spoof trusted domains to impersonate CareConnect360 personnel. | Medium | High | Medium | Anti-Spoofing Controls (DMARC, SPF, DKIM), User Verification Training |
| R4 | Stolen credentials lead to unauthorized access to patient data. | High | High | High | Role-Based Access Control (RBAC), Privileged Access Management (PAM) |
| R5 | Mass phishing campaigns result in account lockouts due to credential stuffing. | Medium | Medium | High | Account Lockout Policies, SIEM Monitoring, Rate Limiting |