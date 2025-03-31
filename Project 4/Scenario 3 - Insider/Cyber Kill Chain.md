# Kill Chain Attack Description: CareConnect360 Insider Attack Scenario

## Stages of the Attack

### Origins
The attack originates from a disgruntled employee, compromised staff member, or malicious insider with legitimate credentials and access to CareConnect360 systems. The motive could be: Financial gain (selling patient data on the dark web). Corporate espionage (leaking medical research to competitors). Personal revenge (sabotaging systems or deleting records) Collusion with external attackers (aiding ransomware or data theft operations).

### Reconnaissance
Since the insider already has access, they conduct passive reconnaissance by: Reviewing security policies to identify gaps.
Identifying unmonitored data repositories (medical records, financial info, admin tools).
Understanding logging & auditing processes to plan ways to evade detection.

### Weaponization
The insider prepares for the attack by: Identifying sensitive data (patient records, billing info, research data).
Creating or exploiting backdoors (modifying access permissions or creating unauthorized accounts).
Establishing exfiltration channels (USB drives, cloud storage, encrypted emails, personal email accounts).

### Delivery
Since the insider already has authorized system access, there’s no need to deliver malware externally. Instead, they: Download large datasets from internal servers onto personal devices. Modify or delete medical records to disrupt healthcare services. Install unauthorized software or scripts for long-term access.

### Exploitation
Exports patient records & financial data from CareConnect360 databases. Escalates privileges to access admin tools, deactivate logging, or disable alerts. Sabotages critical infrastructure (e.g., deleting research data or encrypting files).

### Installation (Persistence)
Creates new admin accounts to maintain access even after leaving the organization. Modifies system configurations to bypass security controls. Uses stolen credentials to access systems remotely from personal devices.

### Actions on Objectives
Once the attack is complete, the insider: Sells or leaks stolen data on the dark web. Destroys or alters patient records to disrupt operations. Covers their tracks by deleting logs & audit trails.