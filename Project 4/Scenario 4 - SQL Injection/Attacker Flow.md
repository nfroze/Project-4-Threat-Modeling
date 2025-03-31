```mermaid
sequenceDiagram
    participant Attacker as Attacker
    participant User as User (Victim)
    participant WebApp as CareConnect360 Web App
    participant Backend as Backend Server (Node.js & Express)
    participant Database as Database (MariaDB)

    activate Attacker
    Attacker->>User: Sends malicious link with SQL injection payload
    User->>WebApp: Clicks link, submits form with injected SQL
    WebApp->>Backend: Passes unsanitized input to API
    deactivate Attacker

    activate Backend
    Backend->>Database: Executes SQL query with injected code
    Database->>Backend: Returns unauthorized sensitive data
    deactivate Backend

    activate Attacker
    Backend->>WebApp: Displays leaked data on frontend
    WebApp->>Attacker: Exposes patient records & credentials
    deactivate Attacker

    activate Attacker
    Attacker->>Database: Modifies/deletes records via injection
    Database->>Attacker: Confirms execution of SQL payload
    deactivate Attacker