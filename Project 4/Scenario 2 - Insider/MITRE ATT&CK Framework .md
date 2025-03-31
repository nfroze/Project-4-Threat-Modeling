# Summary - MITRE ATT&CK Sequence
## Attack Description
An **insider attack** at **CareConnect360** involves a **trusted individual** exploiting their access to **steal, modify, or sell sensitive healthcare data**. Unlike external attacks, **insider threats bypass traditional perimeter defenses**, making them harder to detect.

## Stages of the Attack

### **1. Initial Access**
The insider uses **legitimate credentials** to log into the system.

### **2. Privilege Abuse**
The attacker **escalates privileges** to access **restricted databases** or **patient records**.

### **3. Data Exfiltration**
Sensitive **patient data is stolen, copied to USB/cloud storage, or shared externally**.

### **4. Data Manipulation or System Sabotage**
The attacker may **alter, delete, or corrupt patient records**, disrupting **healthcare services**.

### **5. Covering Tracks**
The insider **clears logs or alters records** to evade detection.

```mermaid
flowchart TD
    %% Define colors for different attack stages
    style Initial_Access fill:#F4D03F,stroke:#000,stroke-width:2px
    style Privilege_Abuse fill:#F5B041,stroke:#000,stroke-width:2px
    style Data_Exfiltration fill:#EB984E,stroke:#000,stroke-width:2px
    style Data_Manipulation fill:#E59866,stroke:#000,stroke-width:2px
    style Cover_Tracks fill:#DC7633,stroke:#000,stroke-width:2px
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px

    %% Attack Sequence
    Initial_Access[Initial Access] -->|Legitimate login using authorized credentials| Privilege_Abuse[Privilege Abuse]
    Privilege_Abuse -->|Access restricted patient records, admin privileges| Data_Exfiltration[Data Exfiltration]
    Data_Exfiltration -->|Copy/export sensitive data to USB, cloud, or external storage| Data_Manipulation[Data Manipulation]
    Data_Manipulation -->|Modify, delete, or corrupt patient records| Cover_Tracks[Covering Tracks]
    Cover_Tracks -->|Clear logs, alter audit trails to hide activity| Cover_Tracks

    %% MITRE ATT&CK Techniques
    subgraph MITRE_Attack[MITRE ATT&CK Techniques]
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px
    Initial_Access -->|T1078 - Valid Accounts| MITRE
    Privilege_Abuse -->|T1078.003 - Local Admin Accounts| MITRE
    Privilege_Abuse -->|T1134 - Access Token Manipulation| MITRE
    Data_Exfiltration -->|T1048 - Exfiltration Over Alternative Protocol| MITRE
    Data_Exfiltration -->|T1567 - Exfiltration Over Web Services| MITRE
    Data_Manipulation -->|T1565.001 - Data Manipulation| MITRE
    Cover_Tracks -->|T1070 - Indicator Removal on Host| MITRE
    Cover_Tracks -->|T1027 - Obfuscated Files or Information| MITRE
    Cover_Tracks -->|T1098 - Account Manipulation| MITRE
    end