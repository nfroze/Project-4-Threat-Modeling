```mermaid
sequenceDiagram
    participant Attacker
    participant User
    participant CareConnect360
    participant BackendServer
    participant Database
    participant CnCServer
    participant PaymentGateway
    
    activate Attacker
    Attacker->>User: Sends phishing email with malicious attachment/link
    User->>Attacker: Clicks on attachment/link (Payload Executed)
    deactivate Attacker
    
    activate User
    User->>CareConnect360: Unknowingly executes malicious file
    CareConnect360->>BackendServer: Malware spreads across network
    deactivate User

    activate BackendServer
    BackendServer->>Database: Encrypts critical patient records
    BackendServer->>CnCServer: Contacts Command & Control (C2) server
    CnCServer->>BackendServer: Issues encryption keys and commands
    deactivate BackendServer

    activate Attacker
    Attacker->>CareConnect360: Displays ransom note demanding payment
    CareConnect360->>PaymentGateway: Attempts to negotiate or pay ransom
    PaymentGateway->>Attacker: Cryptocurrency transaction processed
    deactivate Attacker

    activate BackendServer
    BackendServer->>CnCServer: Requests decryption key (if ransom paid)
    CnCServer->>BackendServer: Decryption key sent (Possibly fake)
    deactivate BackendServer