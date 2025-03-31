# **Risk Summary - Insider Attack on CareConnect360**

## **Risk Table**
| **Risk ID** | **Description** | **Severity** | **Likelihood** | **Impact** | **Controls Required** |
|------------|----------------|-------------|---------------|------------|----------------|
| R1 | Malicious insiders abuse legitimate access to steal patient records. | High | Medium | High | Role-Based Access Control (RBAC), Data Loss Prevention (DLP), User Behavior Analytics (UBA) |
| R2 | Insiders modify or delete critical patient data. | High | Medium | High | File Integrity Monitoring (FIM), Immutable Logs, Privileged Access Management (PAM) |
| R3 | Employees leak sensitive CareConnect360 data for financial gain. | Medium | Medium | High | Data Classification & Monitoring, Strict Data Sharing Policies, Insider Threat Awareness Training |
| R4 | Disgruntled employees disrupt operations by disabling accounts or systems. | Medium | Low | High | Least Privilege Access, SIEM Monitoring, Account Auditing |
| R5 | Former employees retain unauthorized access after termination. | Medium | Low | High | Automated Offboarding Procedures, Access Reviews, MFA on Privileged Accounts |
