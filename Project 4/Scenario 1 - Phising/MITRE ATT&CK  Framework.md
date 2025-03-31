# Summary MITRE ATT&CK Sequence
## Attack Description
A phishing attack on CareConnect360 involves an attacker impersonating a trusted entity to deceive employees into revealing credentials or downloading malware. The attack often relies on social engineering tactics to exploit human error, gaining unauthorized access to sensitive healthcare data and internal systems. Once credentials are stolen or malware is deployed, the attacker can move laterally within the network, escalate privileges, and execute further attacks such as data theft or ransomware deployment.

## Stages of the Attack

### 1. Origins
The attack is initiated by an attacker leveraging a long history of cyber attack techniques. The attacker begins by identifying CareConnect360 as a target due to its sensitive health data and publicly facing infrastructure.

### 2. Reconnaissance
The attacker gathers employee email addresses, domain information, and technology stack details to craft a targeted phishing campaign.

### 3. Weaponization
A malicious email is created, containing either a fake login page that mimics CareConnect360's authentication portal or a malware-laden attachment disguised as an urgent document.

### 4. Delivery
The attacker sends phishing emails to CareConnect360 employees. These emails appear to come from trusted sources, such as IT support, management, or healthcare partners.

### 5. Exploitation
A user clicks on the malicious link or opens the infected attachment, leading to credential theft if a login portal is used or malware execution if the attachment is opened.

### 6. Installation
The attacker gains access through stolen credentials or installs malware to maintain persistence.

### 7. Command & Control (C2)
If malware is present, it communicates with an external server, allowing the attacker to execute commands remotely.

### 8. Actions on Objectives
The attacker can now exfiltrate sensitive patient records, escalate privileges for deeper system access, or deploy additional attacks, such as ransomware.

```mermaid
flowchart TD
    %% Define Colors
    style Reconnaissance fill:#F4D03F,stroke:#000,stroke-width:2px
    style Weaponization fill:#F5B041,stroke:#000,stroke-width:2px
    style Delivery fill:#EB984E,stroke:#000,stroke-width:2px
    style Exploitation fill:#E59866,stroke:#000,stroke-width:2px
    style Installation fill:#DC7633,stroke:#000,stroke-width:2px
    style Command_Control fill:#CA6F1E,stroke:#000,stroke-width:2px
    style Actions_Objectives fill:#BA4A00,stroke:#000,stroke-width:2px
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px
    style Controls fill:#82E0AA,stroke:#000,stroke-width:2px

    %% Attack Flow
    Reconnaissance["Reconnaissance"] -->|"Identify CareConnect360 employees & gather emails"| Weaponization["Weaponization"]
    Weaponization["Weaponization"] -->|"Create phishing emails and fake login pages"| Delivery["Delivery"]
    Delivery["Delivery"] -->|"Send phishing emails targeting employees"| Exploitation["Exploitation"]
    Exploitation["Exploitation"] -->|"User clicks malicious link or opens attachment"| Installation["Installation"]
    Installation["Installation"] -->|"Malware executes or credentials stolen"| Command_Control["Command and Control"]
    Command_Control["Command and Control"] -->|"Establish communication with attacker's server"| Actions_Objectives["Actions on Objectives"]
    Actions_Objectives["Actions on Objectives"] -->|"Exfiltrate stolen credentials or patient records"| Actions_Objectives
    Actions_Objectives["Actions on Objectives"] -->|"Use stolen credentials for privilege escalation"| Actions_Objectives

    %% MITRE ATT&CK Mapping
    subgraph MITRE_Attack["MITRE ATT&CK Techniques"]
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px
    Delivery -->|"T1566.001 - Spear Phishing Link"| MITRE
    Exploitation -->|"T1566.002 - Spear Phishing Attachment"| MITRE
    Exploitation -->|"T1204.002 - User Execution (Malicious Link)"| MITRE
    Installation -->|"T1078 - Valid Accounts (Stolen Credentials)"| MITRE
    Command_Control -->|"T1071 - Application Layer Protocol (C2)"| MITRE
    Actions_Objectives -->|"T1565.001 - Data Manipulation"| MITRE
    end