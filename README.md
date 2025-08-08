# ⚠️ Project 4: Threat Modeling

This project simulates a full-spectrum **threat modeling workshop** for a fictional cloud-based healthcare platform called **CareConnect360**. Built on modern AWS infrastructure and handling sensitive healthcare data (PII/PHI), the system represents a realistic enterprise attack surface — with authentication flows, real-time video, patient portals, and data exchange across services.

The goal is to demonstrate how to proactively identify, assess, and mitigate security risks across a complex cloud-native architecture using industry-standard frameworks:
- **STRIDE** to analyze trust boundaries and architectural risks  
- **MITRE ATT&CK** to map attacker tactics and techniques  
- **Cyber Kill Chain** to simulate attack progression  
- **NIST Incident Response** to build a structured response plan

This project combines architectural thinking, attacker simulation, and security response planning — showcasing where **threat modeling fits into the DevSecOps lifecycle.**

> 🔁 It follows the five core stages of a professional threat modeling workshop:  
> **System Mapping → Threat Enumeration → Attack Simulation → Risk Assessment → Response Planning**

---

## 2. Key Deliverables 📦

- 🗂️ Multi-scenario threat modeling documentation  
- 🧠 STRIDE threat models with per-component risk mapping  
- 🔍 MITRE ATT&CK and Cyber Kill Chain breakdowns  
- 📊 Inherent risk scoring for each scenario  
- 🧯 NIST-aligned response plans per attack  
- 🧱 Architecture visuals: HLD and DFD  
- 👤 Threat actor profiles embedded into each scenario

---

## 3. Threat Modeling Scenarios 🎯

| Scenario | Description | Threat Type |
|----------|-------------|-------------|
| **Scenario 1** | Internal ransomware attack on EC2 fleet | Ransomware (Internal) |
| **Scenario 2** | Insider abuse of S3 access to exfiltrate PHI | Insider Threat |
| **Scenario 3** | SQL Injection via patient portal | External Attack (SQLi) |

Each scenario includes:
- Full attacker flow walkthrough  
- STRIDE, MITRE, and Kill Chain analysis  
- Risk summary and mitigation plan  
- NIST-aligned response strategy

---

## 4. Supporting Materials 🗂️

All deliverables are available in this repository:

- [📄 CareConnect360 – System Overview (PDF)](/docs/CareConnect360.pdf)  
- HLD & DFD diagrams  
- STRIDE threat model tables  
- MITRE ATT&CK mappings  
- Cyber Kill Chain breakdowns  
- Risk assessments  
- Per-scenario threat actor profiles and response plans

---

## 5. Value for Organizations 💡

This project simulates a real-world tabletop-style threat modeling workshop — the kind run by security engineers, architects, or DevSecOps professionals during:

- Secure architecture design  
- Cloud migration planning  
- Regulatory audits (HIPAA, ISO 27001, etc.)  
- Incident response simulations  
- Shift-left security initiatives

It’s designed to show how technical risk can be translated into actionable security decisions — from **code to cloud.**

---

## 6. Conclusion ✅

Threat modeling is not just a checkbox — it’s a mindset.

This project demonstrates how security professionals identify threats **before** attackers do, design controls **before** breaches happen, and plan response strategies **before** the chaos begins.

---

🔗 [Back to my GitHub Profile](https://github.com/nfroze)

> 📌 Built to reflect real-world DevSecOps practice — balancing technical depth, architectural awareness, and proactive security.