# Scenario 1: Ransomware Attack on CareConnect360

## Threat Actor Profile

| Type | Description | Motivation | Access Level |
|------|-------------|------------|--------------|
| Ransomware Operator | External actor using phishing and malware | Financial/extortion | Initial access via phished credentials |

## Attack Flow

1. Phishing email sent to internal user
2. User clicks malicious link
3. Malware establishes persistence on EC2 instance
4. Lateral movement to S3 buckets and databases
5. Data exfiltrated and files encrypted
6. Ransom note deployed

[Full details: Attacker Flow.md](./Attacker%20Flow.md)

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|--------|-----------|-----|
| Initial Access | Phishing: Spearphishing Link | T1566.002 |
| Execution | Command and Scripting Interpreter | T1059 |
| Persistence | Boot or Logon Autostart Execution | T1547 |
| Lateral Movement | Remote Services | T1021 |
| Impact | Data Encrypted for Impact | T1486 |

[Full mapping: MITRE ATT&CK Framework.md](./MITRE%20ATT%26CK%20Framework.md)

## Cyber Kill Chain

| Phase | Description |
|-------|-------------|
| Reconnaissance | Email targets identified in healthcare org |
| Weaponization | Malicious link created and embedded |
| Delivery | Email delivered to user |
| Exploitation | Victim clicks link, payload executes |
| Installation | Malware installs on EC2 and spreads |
| Command & Control | Remote access established |
| Actions on Objective | Data exfiltration and encryption |

[Full detail: Cyber Kill Chain.md](./Cyber%20Kill%20Chain.md)

## STRIDE Analysis

| Component | Threat Type | Description |
|-----------|------------|-------------|
| EC2 Instance | Elevation of Privilege | Malware escalates permissions |
| S3 Bucket | Information Disclosure | Data accessed and exfiltrated |
| Internal Network | Denial of Service | Ransomware encrypts core systems |

[Full breakdown: STRIDE Threat Model.md](./STRIDE%20Threat%20Model.md)

## Risk Assessment

| Likelihood | Impact | Risk Score |
|------------|--------|------------|
| High | High | Critical |

[Details: Risk Summary.md](./Risk%20Summary.md)

## Mitigation and Response

### Prevention
- User training and phishing simulations
- Email filtering and attachment sandboxing
- IAM hardening with MFA and least privilege

### Detection
- CloudTrail monitoring for suspicious EC2 activity
- GuardDuty alerts for unusual network behavior
- SIEM rules for data access anomalies

### Response
- NIST-based incident response playbook
- System isolation procedures
- Backup restoration processes
- Regulatory notification requirements (HIPAA)