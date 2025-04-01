# 🎯 Scenario 1: Ransomware Attack on CareConnect360

This scenario simulates a ransomware attack targeting CareConnect360 — a fictional, cloud-based healthcare platform. The goal is to understand how attackers infiltrate, move laterally, and cause operational disruption or data encryption using real-world techniques.

---

## 1. 👤 Threat Actor Profile

| Type               | Description                                 | Motivation          | Access Level            |
|--------------------|---------------------------------------------|---------------------|--------------------------|
| Ransomware Operator | Financially motivated external actor leveraging phishing and malware | Ransom/extortion     | Initial access via phished credentials |

---

## 2. 🔁 Attack Flow Summary

1. Phishing email sent to internal user
2. User unknowingly clicks malicious link
3. Malware establishes persistence on EC2 instance
4. Lateral movement to S3 buckets and databases
5. Data exfiltrated and files encrypted
6. Ransom note dropped across the platform

*For full details, see [Attacker Flow.md](./Attacker%20Flow.md)*

---

## 3. 🧠 MITRE ATT&CK Mapping

| Tactic              | Technique                               | ID        |
|---------------------|------------------------------------------|-----------|
| Initial Access       | Phishing: Spearphishing Link             | T1566.002 |
| Execution            | Command and Scripting Interpreter        | T1059     |
| Persistence          | Boot or Logon Autostart Execution        | T1547     |
| Lateral Movement     | Remote Services (EC2 lateral access)     | T1021     |
| Impact               | Data Encrypted for Impact                | T1486     |

*For full mapping, see [MITRE ATT&CK Framework.md](./MITRE%20ATT%26CK%20Framework.md)*

---

## 4. 🔗 Cyber Kill Chain Breakdown

| Phase             | Description                                                                 |
|------------------|------------------------------------------------------------------------------|
| Reconnaissance    | Attacker identifies email targets in healthcare org                         |
| Weaponization     | Malicious link created and embedded in phishing email                       |
| Delivery          | Email delivered to unsuspecting user                                        |
| Exploitation      | Victim clicks link, initiating payload execution                            |
| Installation      | Malware installs on EC2 instance and spreads                                |
| Command & Control | Remote access established to internal systems                               |
| Actions on Objective | Exfiltration of data and encryption of files, ransom note displayed     |

*Full detail: [Cyber Kill Chain.md](./Cyber%20Kill%20Chain.md)*

---

## 5. ⚠️ STRIDE Threats Observed

| Component        | Threat Type               | Explanation                                                |
|------------------|---------------------------|------------------------------------------------------------|
| EC2 Instance      | Elevation of Privilege     | Malware escalates permissions on infected machine         |
| S3 Bucket         | Information Disclosure     | Data accessed and exfiltrated during attack                |
| Internal Network  | Denial of Service          | Ransomware halts operations by encrypting core systems     |

*See full breakdown in [STRIDE Threat Model.md](./STRIDE%20Threat%20Model.md)*

---

## 6. 📊 Risk Assessment Summary

| Likelihood | Impact | Risk Score | Notes                                      |
|------------|--------|------------|--------------------------------------------|
| High       | High   | Critical   | Phishing-based ransomware poses major threat to healthcare data availability |

*Details in [Risk Summary.md](./Risk%20Summary.md)*

---

## 7. 🧯 Mitigation & Response Plan

### 🔐 Prevention
- User training and phishing simulations
- Email filtering and attachment sandboxing
- IAM hardening with MFA and least privilege

### 🔍 Detection
- Monitor CloudTrail for suspicious EC2 activity
- GuardDuty alerts for unusual network behavior
- SIEM rules for data access anomalies

### 🚨 Response
- IR playbook based on NIST
- Isolate infected systems
- Restore from clean backups
- Notify authorities and impacted individuals (HIPAA compliance)

---

🔁 [Back to Project 4: Threat Modeling & Incident Response](https://github.com/nfroze/Project-4-Threat-Modeling-Incident-Response)