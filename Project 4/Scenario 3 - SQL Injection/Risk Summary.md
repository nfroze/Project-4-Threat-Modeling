# **Risk Summary - SQL Injection Attack on CareConnect360**

## **Risk Table**
| **Risk ID** | **Description** | **Severity** | **Likelihood** | **Impact** | **Controls Required** |
|------------|----------------|-------------|---------------|------------|----------------|
| R1 | Attackers exploit vulnerable web forms to bypass authentication. | High | High | High | Parameterized Queries, Web Application Firewall (WAF), Multi-Factor Authentication (MFA) |
| R2 | SQL injection is used to modify or delete critical database records. | High | Medium | High | Database Input Validation, Data Integrity Monitoring, Role-Based Access Control (RBAC) |
| R3 | Attackers extract sensitive patient data from the database. | High | High | High | Least Privilege Access, Data Encryption, Database Activity Monitoring (DAM) |
| R4 | Automated SQL injection attacks cause database outages (Denial of Service). | Medium | Medium | High | Query Rate Limiting, Timeouts, Load Balancing |
| R5 | Attackers escalate privileges via SQL injection to gain admin database control. | High | Medium | High | Privileged Access Management (PAM), Security Patching, Regular Code Reviews |