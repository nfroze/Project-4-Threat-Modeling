# Scenario 2: Insider Threat - S3 Data Exfiltration

## Threat Actor Profile

| Type | Description | Motivation | Access Level |
|------|-------------|------------|--------------|
| Malicious Insider | Authenticated employee misusing valid credentials | Financial gain or revenge | Internal (IAM credentials) |

## Attack Flow

1. Insider logs into AWS with valid IAM credentials
2. Navigates to S3 buckets containing PII/PHI data
3. Downloads large amounts of patient records
4. Transfers data to external personal storage
5. Leaves organisation or sells/exposes data

[Full flow: Attacker Flow.md](./Attacker%20Flow.md)

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|--------|-----------|-----|
| Initial Access | Valid Accounts (Insider) | T1078 |
| Collection | Data from Cloud Storage Object | T1530 |
| Exfiltration | Exfiltration Over Alternative Protocol | T1048.003 |
| Defense Evasion | Disabling CloudTrail (attempted) | T1562.008 |

[Full mapping: MITRE ATT&CK Framework.md](./MITRE%20ATT%26CK%20Framework.md)

## Cyber Kill Chain

| Phase | Description |
|-------|-------------|
| Reconnaissance | Insider browses S3 contents for valuable files |
| Delivery | N/A (insider already has access) |
| Exploitation | Misuse of access to download confidential records |
| Installation | N/A |
| Command & Control | Insider sends data to private storage platform |
| Actions on Objective | Data breach involving patient PII |

[Full breakdown: Cyber Kill Chain.md](./Cyber%20Kill%20Chain.md)

## STRIDE Analysis

| Component | Threat Type | Description |
|-----------|------------|-------------|
| S3 Buckets | Information Disclosure | Insider downloads sensitive data |
| IAM Roles | Elevation of Privilege | IAM policy misconfiguration allows broader access |
| Logging Service | Repudiation | Insider attempts to disable activity logs |

[Details: STRIDE Threat Model.md](./STRIDE%20Threat%20Model.md)

## Risk Assessment

| Likelihood | Impact | Risk Score |
|------------|--------|------------|
| Medium | High | High |

[Details: Risk Summary.md](./Risk%20Summary.md)

## Mitigation and Response

### Prevention
- Enforce strict IAM least privilege
- Mandatory access reviews and approval workflows
- Segregate access based on job role

### Detection
- Enable CloudTrail logging for all S3 API calls
- Monitor for unusual download patterns
- Anomaly detection via GuardDuty or SIEM

### Response
- Suspend compromised IAM credentials
- Notify compliance teams and legal (HIPAA)
- Forensic analysis and user access review
- Update security policies to close control gaps