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
    Spoofing["🔓 Spoofing: Insider impersonates another user via shared credentials"]
    Tampering["⚠️ Tampering: Insider modifies or deletes patient records"]
    Repudiation["📜 Repudiation: Insider denies unauthorized actions"]
    Info_Disclosure["🔍 Information Disclosure: Insider leaks patient data"]
    Denial_of_Service["⛔ Denial of Service: Insider disables accounts or disrupts services"]
    Elevation_of_Privilege["🚀 Elevation of Privilege: Insider gains admin-level access"]

    %% Attack Flow
    Insider["🕵️‍♂️ Malicious Insider"] -->|Uses compromised or shared credentials| Spoofing
    Spoofing -->|Accesses sensitive patient records| Info_Disclosure
    Info_Disclosure -->|Steals and exfiltrates data| Tampering
    Tampering -->|Modifies patient records to cover tracks| Repudiation
    Repudiation -->|Deletes system logs| Denial_of_Service
    Denial_of_Service -->|Disables critical services, impacting operations| Elevation_of_Privilege
    Elevation_of_Privilege -->|Escalates privileges to gain admin access| Insider

    %% Mitigation Controls
    subgraph Security_Controls["🛡️ Mitigation Controls"]
    MFA["🔑 Multi-Factor Authentication"]
    PAM["🔒 Privileged Access Management (PAM)"]
    UBA["📊 User Behavior Analytics (UBA)"]
    SIEM["📜 SIEM Logging & Monitoring"]
    DLP["🚨 Data Loss Prevention (DLP)"]
    RBAC["⚖️ Role-Based Access Control (RBAC)"]
    Immutable_Logs["📝 Immutable Logging"]
    end

    %% Linking Mitigations
    Spoofing -->|Prevented by| MFA
    Tampering -->|Logged by| Immutable_Logs
    Repudiation -->|Tracked in| SIEM
    Info_Disclosure -->|Blocked by| DLP
    Denial_of_Service -->|Mitigated by| RBAC
    Elevation_of_Privilege -->|Restricted by| PAM
    Elevation_of_Privilege -->|Detected via| UBA