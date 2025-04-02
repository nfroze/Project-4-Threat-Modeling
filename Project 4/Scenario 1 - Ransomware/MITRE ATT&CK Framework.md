# Summary - MITRE ATT&CK Sequence
## Attack Description
A ransomware attack on CareConnect360 follows a structured sequence where attackers infiltrate the system, encrypt critical patient data, and demand ransom. This attack targets vulnerabilities in system defenses, exploits weak access controls, and spreads laterally through the network.

## Stages of the Attack

### **1. Reconnaissance**
The attacker conducts research to identify vulnerabilities in CareConnect360's **public-facing applications, remote access points, and user credentials**.

### **2. Initial Access**
The attacker gains entry via **phishing, exploiting vulnerabilities, or using stolen credentials**.

### **3. Execution**
The attacker **deploys the ransomware payload**, encrypting **critical patient records and system files**.

### **4. Persistence**
The ransomware **establishes a foothold**, ensuring it remains active even after system reboots.

### **5. Privilege Escalation & Lateral Movement**
The attacker **gains administrative privileges** and **spreads ransomware** across the network.

### **6. Impact & Exfiltration**
The attacker **encrypts or exfiltrates** patient data, followed by **ransom demands**.