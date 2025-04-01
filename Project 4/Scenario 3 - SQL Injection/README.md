# 🎯 Scenario 3: SQL Injection on Patient Portal

This scenario simulates a SQL Injection (SQLi) attack targeting the public-facing patient portal of CareConnect360. The attacker exploits poor input validation to exfiltrate sensitive backend data via unauthenticated access.

The goal is to demonstrate how a single overlooked validation flaw can lead to significant data compromise — even from outside the organization.

---

## 1. 👤 Threat Actor Profile

| Type             | Description                                 | Motivation       | Access Level     |
|------------------|---------------------------------------------|------------------|------------------|
| External Attacker | Unauthenticated user exploiting web input  | Financial gain or notoriety | None (public access) |

---

## 2. 🔁 Attack Flow Summary

1. Attacker discovers injectable input field on the patient portal  
2. Sends specially crafted SQL payload via login or search form  
3. Backend query returns unauthorized data (e.g., patient records)  
4. Attacker escalates the injection to enumerate full database  
5. Exfiltrates data and attempts to cover tracks

*For complete breakdown, see [Attacker Flow.md](./Attacker%20Flow.md)*

---

## 3. 🧠 MITRE ATT&CK Mapping

| Tactic              | Technique                            | ID        |
|---------------------|---------------------------------------|-----------|
| Initial Access       | Exploit Public-Facing Application    | T1190     |
| Collection           | Automated Collection (Database Dump) | T1119     |
| Exfiltration         | Exfiltration Over Web Protocol       | T1041     |
| Defense Evasion      | Input Obfuscation                    | T1001.003 |

*See full mapping: [MITRE ATT&CK Framework.md](./MITRE%20ATT%26CK%20Framework.md)*

---

## 4. 🔗 Cyber Kill Chain Breakdown

| Phase             | Description                                                                   |
|------------------|--------------------------------------------------------------------------------|
| Reconnaissance    | Attacker probes web inputs for weak validation                                |
| Weaponization     | SQL payload crafted for login/search forms                                    |
| Delivery          | Payload submitted via public-facing web form                                  |
| Exploitation      | SQL logic injected, exposing data from backend                                |
| Installation      | N/A                                                                            |
| Command & Control | Continued queries issued to dump large data sets                              |
| Actions on Objective | Sensitive PII exfiltrated and potentially sold or leaked                   |

*Detailed breakdown in [Cyber Kill Chain Summary.md](./Cyber%20Kill%20Chain%20Summary.md)*

---

## 5. ⚠️ STRIDE Threats Observed

| Component        | Threat Type             | Explanation                                               |
|------------------|--------------------------|-----------------------------------------------------------|
| Web Application  | Tampering                | Input manipulated to alter query logic                    |
| Database         | Information Disclosure   | Unauthorized access to protected records via SQLi         |
| Logs             | Repudiation              | Attacker avoids detection by bypassing logging mechanisms |

*See full STRIDE table: [STRIDE Threat Model.md](./STRIDE%20Threat%20Model.md)*

---

## 6. 📊 Risk Assessment Summary

| Likelihood | Impact | Risk Score | Notes                                                   |
|------------|--------|------------|-----------------------------------------------------------|
| High       | High   | Critical   | SQLi is one of the most common and damaging web attack vectors |

*See: [Risk Summary.md](./Risk%20Summary.md)*

---

## 7. 🧯 Mitigation & Response Plan

### 🔐 Prevention
- Implement strong input validation and prepared statements
- Apply WAF rules to block malicious input patterns
- Sanitize all user-supplied data before executing queries

### 🔍 Detection
- Monitor application logs for unusual input patterns
- Alert on large/unusual SELECT queries from unauthenticated users
- Use DAST tools (e.g., OWASP ZAP) for regular scanning

### 🚨 Response
- Block offending IPs at the WAF level
- Rotate database credentials and review access logs
- Conduct post-incident forensic analysis
- Patch vulnerable input points and push hotfix immediately

---

🔁 [Back to Project 4: Threat Modeling & Incident Response](https://github.com/nfroze/Project-4-Threat-Modeling-Incident-Response)