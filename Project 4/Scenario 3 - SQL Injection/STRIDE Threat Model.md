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

```mermaid
flowchart TD
    %% Define STRIDE Categories and Styling
    style Spoofing fill:#F4D03F,stroke:#000,stroke-width:2px
    style Tampering fill:#F5B041,stroke:#000,stroke-width:2px
    style Repudiation fill:#EB984E,stroke:#000,stroke-width:2px
    style Info_Disclosure fill:#E59866,stroke:#000,stroke-width:2px
    style Denial_of_Service fill:#DC7633,stroke:#000,stroke-width:2px
    style Elevation_of_Privilege fill:#CA6F1E,stroke:#000,stroke-width:2px
    style Controls fill:#82E0AA,stroke:#000,stroke-width:2px

    %% STRIDE Threat Categories
    Spoofing["🔓 Spoofing: Attacker bypasses authentication via SQL Injection"]
    Tampering["⚠️ Tampering: SQL Injection modifies or deletes database records"]
    Repudiation["📜 Repudiation: Attackers erase logs to cover SQL Injection traces"]
    Info_Disclosure["🔍 Information Disclosure: SQL Injection extracts sensitive patient records"]
    Denial_of_Service["⛔ Denial of Service: SQL Injection overloads the database, causing downtime"]
    Elevation_of_Privilege["🚀 Elevation of Privilege: Attackers escalate access to gain admin rights"]

    %% Attack Flow
    Attacker["🎭 Attacker"] -->|Injects malicious SQL into web form| Spoofing
    Spoofing -->|Bypasses authentication & gains access| Tampering
    Tampering -->|Modifies or deletes patient records| Info_Disclosure
    Info_Disclosure -->|Steals sensitive data from the database| Denial_of_Service
    Denial_of_Service -->|Executes heavy SQL queries to overload the database| Repudiation
    Repudiation -->|Deletes logs to hide attack traces| Elevation_of_Privilege
    Elevation_of_Privilege -->|Escalates privileges to gain full admin control| Attacker

    %% Mitigation Controls
    subgraph Security_Controls["🛡️ Mitigation Controls"]
    Parameterized_Queries["🔑 Parameterized Queries & Prepared Statements"]
    WAF["🛡️ Web Application Firewall (WAF)"]
    MFA["🔒 Multi-Factor Authentication (MFA)"]
    Data_Validation["✅ Strict Input Validation"]
    DAM["📊 Database Activity Monitoring (DAM)"]
    SIEM["📜 SIEM Logging & Centralized Logs"]
    Least_Privilege["⚖️ Least Privilege & Role-Based Access"]
    Rate_Limiting["⏳ Query Rate Limiting & Timeouts"]
    PAM["🔐 Privileged Access Management (PAM)"]
    end

    %% Linking Mitigations
    Spoofing -->|Prevented by| MFA
    Tampering -->|Blocked by| Data_Validation
    Repudiation -->|Logged in| SIEM
    Info_Disclosure -->|Prevented by| WAF
    Denial_of_Service -->|Mitigated by| Rate_Limiting
    Elevation_of_Privilege -->|Restricted by| PAM
    Elevation_of_Privilege -->|Reduced by| Least_Privilege