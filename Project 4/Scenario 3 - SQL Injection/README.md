# Scenario 3: SQL Injection on Patient Portal

## Threat Actor Profile

| Type | Description | Motivation | Access Level |
|------|-------------|------------|--------------|
| External Attacker | Unauthenticated user exploiting web input | Financial gain or notoriety | None (public access) |

## Attack Flow

1. Attacker discovers injectable input field on patient portal
2. Sends crafted SQL payload via login or search form
3. Backend query returns unauthorised patient records
4. Attacker escalates injection to enumerate full database
5. Exfiltrates data and attempts to cover tracks

[Complete breakdown: Attacker Flow.md](./Attacker%20Flow.md)

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|--------|-----------|-----|
| Initial Access | Exploit Public-Facing Application | T1190 |
| Collection | Automated Collection (Database Dump) | T1119 |
| Exfiltration | Exfiltration Over Web Protocol | T1041 |
| Defense Evasion | Input Obfuscation | T1001.003 |

[Full mapping: MITRE ATT&CK Framework.md](./MITRE%20ATT%26CK%20Framework.md)

## Cyber Kill Chain

| Phase | Description |
|-------|-------------|
| Reconnaissance | Attacker probes web inputs for weak validation |
| Weaponization | SQL payload crafted for login/search forms |
| Delivery | Payload submitted via public web form |
| Exploitation | SQL logic injected, exposing backend data |
| Installation | N/A |
| Command & Control | Continued queries to dump data sets |
| Actions on Objective | PII exfiltrated and potentially sold or leaked |

[Detailed breakdown: Cyber Kill Chain Summary.md](./Cyber%20Kill%20Chain%20Summary.md)

## STRIDE Analysis

| Component | Threat Type | Description |
|-----------|------------|-------------|
| Web Application | Tampering | Input manipulated to alter query logic |
| Database | Information Disclosure | Unauthorised access to protected records via SQLi |
| Logs | Repudiation | Attacker avoids detection by bypassing logging |

[Full table: STRIDE Threat Model.md](./STRIDE%20Threat%20Model.md)

## Risk Assessment

| Likelihood | Impact | Risk Score |
|------------|--------|------------|
| High | High | Critical |

[Details: Risk Summary.md](./Risk%20Summary.md)

## Mitigation and Response

### Prevention
- Implement input validation and prepared statements
- Apply WAF rules to block malicious patterns
- Sanitise all user-supplied data before queries

### Detection
- Monitor application logs for unusual input patterns
- Alert on large SELECT queries from unauthenticated users
- Regular DAST scanning (OWASP ZAP)

### Response
- Block offending IPs at WAF level
- Rotate database credentials and review access logs
- Conduct forensic analysis
- Patch vulnerable input points immediately