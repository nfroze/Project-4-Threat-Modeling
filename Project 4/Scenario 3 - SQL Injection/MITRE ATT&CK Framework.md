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
