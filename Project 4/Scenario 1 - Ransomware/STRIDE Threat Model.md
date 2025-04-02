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