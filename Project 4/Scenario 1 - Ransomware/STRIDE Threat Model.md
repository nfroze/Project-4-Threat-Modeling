# **STRIDE Threat Model - Ransomware Attack on CareConnect360**

## **STRIDE Threat Analysis Table**
| **STRIDE Category**       | **How It Relates to Ransomware on CareConnect360** | **Mitigation Controls** |
|---------------------------|---------------------------------|----------------|
| **S - Spoofing**          | Attackers impersonate IT support or software vendors to trick users into installing ransomware. | Digital Signature Validation, Security Awareness Training, Endpoint Protection |
| **T - Tampering**         | Ransomware modifies or encrypts patient records, making them inaccessible. | File Integrity Monitoring (FIM), Secure Backups, Endpoint Detection & Response (EDR) |
| **R - Repudiation**       | Attackers delete system logs to hide traces of ransomware execution. | Centralized SIEM Logging, Immutable Logs, Audit Trails |
| **I - Information Disclosure** | Some ransomware strains exfiltrate sensitive patient data before encrypting files. | Data Loss Prevention (DLP), Network Segmentation, Encryption at Rest & In Transit |
| **D - Denial of Service** | Ransomware disrupts healthcare operations by locking out critical files and systems. | Regular Backups, Business Continuity Planning (BCP), Ransomware Detection Policies |
| **E - Elevation of Privilege** | Ransomware exploits privilege escalation vulnerabilities to spread across CareConnect360’s infrastructure. | Least Privilege Access, Privileged Access Management (PAM), Patch Management |

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
    Spoofing["🔓 Spoofing: Attacker impersonates IT support/software vendor"]
    Tampering["⚠️ Tampering: Ransomware encrypts or modifies patient records"]
    Repudiation["📜 Repudiation: Attackers delete system logs to cover tracks"]
    Info_Disclosure["🔍 Information Disclosure: Ransomware exfiltrates patient records"]
    Denial_of_Service["⛔ Denial of Service: Ransomware locks critical systems"]
    Elevation_of_Privilege["🚀 Elevation of Privilege: Malware escalates privileges to spread network-wide"]

    %% Attack Flow
    Attacker["🎭 Attacker"] -->|Delivers ransomware via phishing or exploit| Spoofing
    Spoofing -->|User downloads infected file or clicks malicious link| Tampering
    Tampering -->|Ransomware encrypts patient records| Info_Disclosure
    Info_Disclosure -->|Attacker demands ransom or sells stolen data| Denial_of_Service
    Denial_of_Service -->|Systems become inaccessible, disrupting operations| Repudiation
    Repudiation -->|Attacker deletes logs to prevent forensic investigation| Elevation_of_Privilege

    %% Mitigation Controls
    subgraph Security_Controls["🛡️ Mitigation Controls"]
    Digital_Signatures["🔑 Digital Signature Validation"]
    Awareness_Training["📚 Security Awareness Training"]
    Endpoint_Protection["🖥️ Endpoint Protection & Web Filtering"]
    SIEM_Monitoring["📊 SIEM Logging & Monitoring"]
    Role_Based_Access["🔒 Role-Based Access Control (RBAC)"]
    Least_Privilege["⚖️ Least Privilege & PAM"]
    Regular_Backups["💾 Regular Offline Backups"]
    Network_Segmentation["🛡️ Network Segmentation"]
    Patch_Management["🛠️ Regular Patch Management"]
    end

    %% Linking Mitigations
    Spoofing -->|Prevented by| Digital_Signatures
    Tampering -->|Blocked by| Endpoint_Protection
    Repudiation -->|Logged in| SIEM_Monitoring
    Info_Disclosure -->|Prevented by| Network_Segmentation
    Denial_of_Service -->|Reduced by| Regular_Backups
    Elevation_of_Privilege -->|Mitigated by| Least_Privilege
    Elevation_of_Privilege -->|Patched via| Patch_Management