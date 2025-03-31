```mermaid
sequenceDiagram
    participant Insider as Insider (Malicious Employee)
    participant CareConnect360 as CareConnect360 System
    participant Database as Database (MariaDB)
    participant ExternalDrive as External Storage (USB/Cloud)
    participant DarkWeb as Dark Web/Competitor

    activate Insider
    Insider->>CareConnect360: Logs into system using valid credentials
    CareConnect360->>Insider: Provides authorized access to patient data
    deactivate Insider

    activate Insider
    Insider->>Database: Executes unauthorized queries to extract sensitive data
    Database->>Insider: Returns patient records and PII
    deactivate Insider

    activate Insider
    Insider->>ExternalDrive: Copies extracted data to USB/Cloud storage
    deactivate Insider

    activate Insider
    Insider->>DarkWeb: Sells or leaks patient data for financial gain
    DarkWeb->>Insider: Confirms transaction and payment
    deactivate Insider