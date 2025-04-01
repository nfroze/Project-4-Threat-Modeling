# 🎯 Scenario 2: Insider Threat – S3 Data Exfiltration

This scenario simulates a malicious insider attack targeting CareConnect360’s sensitive patient records. An employee with legitimate access to AWS resources exfiltrates large volumes of data from S3 buckets.

The goal is to highlight risks posed by internal actors with elevated permissions and demonstrate how access misuse can bypass perimeter defenses.

---

## 1. 👤 Threat Actor Profile

| Type           | Description                              | Motivation        | Access Level           |
|----------------|------------------------------------------|-------------------|-------------------------|
| Malicious Insider | Authenticated employee misusing valid credentials | Financial gain or revenge | Internal (IAM credentials) |

---

## 2. 🔁 Attack Flow Summary

1. Insider logs into AWS environment with valid IAM user credentials  
2. Navigates to S3 buckets containing PII/PHI data  
3. Downloads large amounts of sensitive patient records  
4. Transfers data to external personal storage  
5. Leaves organization or sells/exposes data

*For full flow, see [Attacker Flow.md](./Attacker%20Flow.md)*

---

## 3. 🧠 MITRE ATT&CK Mapping

| Tactic            | Technique                              | ID        |
|-------------------|-----------------------------------------|-----------|
| Initial Access     | Valid Accounts (Insider)                | T1078     |
| Collection         | Data from Cloud Storage Object         | T1530     |
| Exfiltration       | Exfiltration Over Alternative Protocol | T1048.003 |
| Defense Evasion    | Disabling CloudTrail (attempted)        | T1562.008 |

*See full mapping: [MITRE ATT&CK Framework.md](./MITRE%20ATT%26CK%20Framework.md)*

---

## 4. 🔗 Cyber Kill Chain Breakdown

| Phase             | Description                                                                 |
|------------------|------------------------------------------------------------------------------|
| Reconnaissance    | Insider browses S3 contents for valuable files                              |
| Delivery          | N/A (insider already has access)                                            |
| Exploitation      | Misuse of access to download confidential records                           |
| Installation      | N/A                                                                          |
| Command & Control | Insider sends data to private storage platform                              |
| Actions on Objective | Data breach involving patient PII                                        |

*See full breakdown: [Cyber Kill Chain.md](./Cyber%20Kill%20Chain.md)*

---

## 5. ⚠️ STRIDE Threats Observed

| Component     | Threat Type             | Explanation                                          |
|---------------|--------------------------|------------------------------------------------------|
| S3 Buckets     | Information Disclosure   | Insider downloads sensitive data                     |
| IAM Roles      | Elevation of Privilege   | IAM policy misconfig allows broader access than needed |
| Logging Service| Repudiation              | Insider attempts to disable activity logs            |

*See: [STRIDE Threat Model.md](./STRIDE%20Threat%20Model.md)*

---

## 6. 📊 Risk Assessment Summary

| Likelihood | Impact | Risk Score | Notes                                                  |
|------------|--------|------------|----------------------------------------------------------|
| Medium     | High   | High       | Insider risks are difficult to detect and highly damaging |

*See: [Risk Summary.md](./Risk%20Summary.md)*

---

## 7. 🧯 Mitigation & Response Plan

### 🔐 Prevention
- Enforce strict IAM least privilege
- Mandatory access reviews and approval workflows
- Segregate access based on job role

### 🔍 Detection
- Enable CloudTrail logging for all S3 API calls
- Monitor for unusual download patterns
- Use anomaly detection via GuardDuty or SIEM

### 🚨 Response
- Suspend compromised IAM credentials
- Notify compliance teams and legal (HIPAA implications)
- Forensic analysis and user access review
- Update security policies to close control gaps

---

🔁 [Back to Project 4: Threat Modeling & Incident Response](https://github.com/nfroze/Project-4-Threat-Modeling-Incident-Response)
