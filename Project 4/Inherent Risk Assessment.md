# Inherent Risk Assessment - CareConnect360

| **Risk ID** | **Risk Description**                                     | **Impact** | **Likelihood** | **Overall Risk Level** |
|------------|-------------------------------------------------|---------|-------------|------------------|
| R-001      | Unauthorized access to patient data (PII)       | High    | High        | Critical         |
| R-002      | Data breach due to API vulnerabilities          | High    | Medium      | High             |
| R-003      | Unencrypted data transmission                   | High    | Medium      | High             |
| R-004      | Weak authentication (brute force attacks)       | High    | High        | Critical         |
| R-005      | Denial of Service (DoS) attack on backend APIs  | Medium  | High        | High             |
| R-006      | Insider threats from healthcare providers       | High    | Low         | Medium           |
| R-007      | Failure to comply with HIPAA regulations        | High    | Medium      | High             |
| R-008      | Data loss due to improper cloud storage config  | High    | Medium      | High             |
| R-009      | Misconfigured IAM roles exposing sensitive data | High    | Medium      | High             |
| R-010      | Lack of monitoring/logging for security events  | Medium  | High        | High             |
| R-011      | Phishing attacks targeting healthcare providers | Medium  | High        | High             |
| R-012      | Software supply chain vulnerabilities           | High    | Medium      | High             |
| R-013      | WebRTC eavesdropping in Telehealth sessions     | High    | Medium      | High             |
| R-014      | Insecure third-party API integrations          | High    | Medium      | High             |
| R-015      | Lack of security updates/patching              | High    | Medium      | High             |

### **Risk Level Definitions**
- **Critical** (🔴) – Requires **immediate attention**, poses a serious threat to the system.
- **High** (🟠) – Needs **prompt mitigation**, could lead to significant security risks.
- **Medium** (🟡) – Should be addressed **in a timely manner**, potential for exploitation.
- **Low** (🟢) – **Monitored** but does not pose an immediate risk.