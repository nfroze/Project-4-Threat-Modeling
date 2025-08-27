# Project 4: Threat Modeling

## Overview

Threat modeling exercise for fictional healthcare platform CareConnect360. Analysis of potential security risks using industry frameworks on cloud-based architecture handling healthcare data.

## Frameworks Used

- STRIDE: Trust boundary and architectural risk analysis
- MITRE ATT&CK: Attacker tactics and techniques mapping
- Cyber Kill Chain: Attack progression simulation
- NIST Incident Response: Structured response planning

## Threat Modeling Process

1. System Mapping
2. Threat Enumeration
3. Attack Simulation
4. Risk Assessment
5. Response Planning

## Scenarios Analysed

| Scenario | Description | Threat Type |
|----------|-------------|-------------|
| Scenario 1 | Ransomware attack on EC2 fleet | Ransomware (Internal) |
| Scenario 2 | S3 access abuse for PHI exfiltration | Insider Threat |
| Scenario 3 | SQL Injection via patient portal | External Attack (SQLi) |

## Deliverables

Each scenario includes:
- Attacker flow walkthrough
- STRIDE analysis
- MITRE ATT&CK mapping
- Cyber Kill Chain breakdown
- Risk assessment
- Mitigation recommendations
- NIST-aligned response strategy

## Documentation

- [CareConnect360 System Overview (PDF)](/docs/CareConnect360.pdf)
- HLD and DFD diagrams
- STRIDE threat model tables
- MITRE ATT&CK mappings
- Risk assessments
- Response plans

## Workshop Format

Simulated 3-hour threat modeling workshop including:
- Engineering team perspective
- Product management considerations
- DevSecOps requirements
- Risk assessment methodology

## Technologies Analysed

- AWS infrastructure (EC2, S3, RDS)
- Healthcare data handling (PHI/PII)
- Authentication systems
- Patient portal applications
- Real-time communication services