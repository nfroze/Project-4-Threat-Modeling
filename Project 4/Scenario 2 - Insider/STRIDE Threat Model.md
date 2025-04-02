# **STRIDE Threat Model - Insider Attack on CareConnect360**

## **STRIDE Threat Analysis Table**
| **STRIDE Category**       | **How It Relates to Insider Attacks on CareConnect360** | **Mitigation Controls** |
|---------------------------|---------------------------------|----------------|
| **S - Spoofing**          | Malicious insiders may impersonate other employees by using shared credentials or compromised accounts. | Multi-Factor Authentication (MFA), Privileged Access Management (PAM), User Behavior Analytics (UBA) |
| **T - Tampering**         | Insiders with access to patient records can alter or delete medical data. | Data Integrity Monitoring, Role-Based Access Control (RBAC), Audit Logs |
| **R - Repudiation**       | Insiders may deny accessing, modifying, or exfiltrating data. | Immutable Logs, Non-Repudiation Mechanisms, SIEM Logging |
| **I - Information Disclosure** | Insiders can steal or leak sensitive patient data for personal gain. | Data Loss Prevention (DLP), File Access Monitoring, Strict Access Controls |
| **D - Denial of Service** | Employees with admin privileges can deliberately lock out users or disable critical systems. | Least Privilege Access, Access Reviews, Network Segmentation |
| **E - Elevation of Privilege** | Malicious insiders may escalate privileges to gain unauthorized access to administrative functions. | Privileged Access Management (PAM), Regular Security Audits, Zero Trust Architecture |