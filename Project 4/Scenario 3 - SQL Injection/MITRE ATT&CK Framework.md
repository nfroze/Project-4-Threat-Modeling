# Summary - MITRE ATT&CK Sequence
## Attack Description
A **SQL Injection (SQLi) attack** occurs when an attacker injects **malicious SQL code** into input fields or API requests to **manipulate the backend database**. If successful, the attacker can **steal sensitive patient records, modify healthcare data, or execute administrative commands** on the database.

## Stages of the Attack

### **1. Reconnaissance**
The attacker scans the **CareConnect360 web application** for **SQL injection vulnerabilities** in **search fields, login forms, and API requests**.

### **2. Exploitation**
By injecting **malicious SQL payloads**, the attacker bypasses **authentication** or **extracts sensitive medical records**.

### **3. Data Exfiltration**
The attacker **retrieves patient records, credentials, or financial data** from the **MariaDB database**.

### **4. Data Manipulation**
The attacker **modifies, deletes, or corrupts critical patient information**.

### **5. Persistence & Covering Tracks**
The attacker **creates backdoor accounts**, hides logs, or **alters system configurations** to maintain access.

```mermaid
flowchart TD
    %% Define colors for different attack stages
    style Reconnaissance fill:#F4D03F,stroke:#000,stroke-width:2px
    style Exploitation fill:#F5B041,stroke:#000,stroke-width:2px
    style Data_Exfiltration fill:#EB984E,stroke:#000,stroke-width:2px
    style Data_Manipulation fill:#E59866,stroke:#000,stroke-width:2px
    style Persistence fill:#DC7633,stroke:#000,stroke-width:2px
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px

    %% Attack Sequence
    Reconnaissance[Reconnaissance] -->|Scan CareConnect360 for SQL Injection vulnerabilities| Exploitation[Exploitation]
    Exploitation -->|Inject malicious SQL payload into input fields/API requests| Data_Exfiltration[Data Exfiltration]
    Data_Exfiltration -->|Retrieve sensitive patient records| Data_Manipulation[Data Manipulation]
    Data_Manipulation -->|Modify, delete, or corrupt patient records| Persistence[Persistence]
    Persistence -->|Create backdoor admin accounts, hide logs| Persistence

    %% MITRE ATT&CK Techniques
    subgraph MITRE_Attack[MITRE ATT&CK Techniques]
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px
    Reconnaissance -->|T1595 - Active Scanning| MITRE
    Exploitation -->|T1190 - Exploit Public-Facing Application| MITRE
    Exploitation -->|T1059.003 - Command and Scripting Interpreter| MITRE
    Data_Exfiltration -->|T1041 - Exfiltration Over C2 Channel| MITRE
    Data_Manipulation -->|T1565.001 - Data Manipulation| MITRE
    Persistence -->|T1136 - Create Account| MITRE
    Persistence -->|T1098 - Account Manipulation| MITRE
    Persistence -->|T1070 - Indicator Removal on Host| MITRE
    end