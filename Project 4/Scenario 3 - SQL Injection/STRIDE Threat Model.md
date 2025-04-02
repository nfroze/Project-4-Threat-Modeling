# **STRIDE Threat Model - SQL Injection Attack on CareConnect360**

## **STRIDE Threat Analysis Table**
| **STRIDE Category**       | **How It Relates to SQL Injection on CareConnect360** | **Mitigation Controls** |
|---------------------------|---------------------------------|----------------|
| **S - Spoofing**          | Attackers manipulate input fields to impersonate users by bypassing authentication via SQL injection. | Parameterized Queries, Web Application Firewall (WAF), Multi-Factor Authentication (MFA) |
| **T - Tampering**         | SQL injection allows attackers to modify or delete critical patient records. | Database Input Validation, Data Integrity Monitoring, Role-Based Access Control (RBAC) |
| **R - Repudiation**       | Attackers may alter logs or delete evidence of malicious database activity. | Immutable Logs, Database Activity Monitoring (DAM), Centralized SIEM Logging |
| **I - Information Disclosure** | SQL injection exposes sensitive patient records stored in the database. | Data Encryption, Least Privilege Access, Web Application Firewall (WAF) |
| **D - Denial of Service** | SQL injection can overload the database with resource-intensive queries, causing downtime. | Query Rate Limiting, Timeouts, Load Balancing |
| **E - Elevation of Privilege** | Attackers exploit SQL injection to escalate privileges and gain administrative database access. | Least Privilege Access, Privileged Access Management (PAM), Regular Security Audits |