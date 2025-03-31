# **STRIDE Threat Model - Phishing Attack on CareConnect360**

## **STRIDE Threat Analysis Table**
| **STRIDE Category**       | **How It Relates to Phishing on CareConnect360** | **Mitigation Controls** |
|---------------------------|---------------------------------|----------------|
| **S - Spoofing**          | Attackers impersonate CareConnect360 employees or vendors to trick users into revealing credentials. | Multi-Factor Authentication (MFA), Email Security (DMARC, SPF, DKIM) |
| **T - Tampering**         | Phishing emails contain malicious links that modify login requests or inject malware. | Web Filtering, Email Scanning, Endpoint Protection |
| **R - Repudiation**       | Users who fall victim to phishing may deny clicking links or submitting credentials. | Audit Logging, Email Archiving, SIEM Monitoring |
| **I - Information Disclosure** | Stolen credentials allow attackers to access patient records and sensitive CareConnect360 data. | Data Encryption, Role-Based Access Control (RBAC), User Awareness Training |
| **D - Denial of Service** | Phishing campaigns can lead to account lockouts due to mass credential stuffing attacks. | Account Lockout Policies, Rate Limiting, SIEM Alerts |
| **E - Elevation of Privilege** | Attackers use stolen credentials to escalate privileges and gain admin access to CareConnect360 systems. | Least Privilege Access, Privileged Access Management (PAM), Regular Permission Audits |

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
    Spoofing["🔓 Spoofing: Attacker impersonates CareConnect360 employee/vendor"]
    Tampering["⚠️ Tampering: Phishing email contains malicious link or malware"]
    Repudiation["📜 Repudiation: User denies clicking link or providing credentials"]
    Info_Disclosure["🔍 Information Disclosure: Stolen credentials expose patient records"]
    Denial_of_Service["⛔ Denial of Service: Credential stuffing locks accounts"]
    Elevation_of_Privilege["🚀 Elevation of Privilege: Stolen credentials used for admin access"]

    %% Attack Flow
    Attacker["🎭 Attacker"] -->|Sends phishing email| Spoofing
    Spoofing -->|Tricks user into clicking| Tampering
    Tampering -->|Malicious link steals credentials| Info_Disclosure
    Info_Disclosure -->|Attacker gains system access| Elevation_of_Privilege
    Info_Disclosure -->|Data breach, access to patient records| Denial_of_Service
    Denial_of_Service -->|Multiple failed attempts lock accounts| Repudiation

    %% Mitigation Controls
    subgraph Security_Controls["🛡️ Mitigation Controls"]
    MFA["🔑 Multi-Factor Authentication"]
    Email_Security["📧 Email Security (DMARC, SPF, DKIM)"]
    Endpoint_Protection["🖥️ Endpoint Protection & Web Filtering"]
    SIEM_Monitoring["📊 SIEM Logging & Monitoring"]
    Role_Based_Access["🔒 Role-Based Access Control (RBAC)"]
    Least_Privilege["⚖️ Least Privilege & PAM"]
    end

    %% Linking Mitigations
    Spoofing -->|Mitigated by| MFA
    Tampering -->|Blocked by| Email_Security
    Repudiation -->|Logged in| SIEM_Monitoring
    Info_Disclosure -->|Prevented by| Role_Based_Access
    Denial_of_Service -->|Reduced by| SIEM_Monitoring
    Elevation_of_Privilege -->|Prevented by| Least_Privilege