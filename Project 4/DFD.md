```mermaid
flowchart TD;
    %% External Entities
    Patients["👤 Patients"] -->|Login, Schedule, View Records| Frontend["🌐 CareConnect360 Web App"]
    HealthcareProviders["🏥 Providers"] -->|Manage Patients, Appointments| Frontend
    ThirdParty["🔗 Third-Party APIs"] -->|Send/Receive Data| Backend["⚙️ Backend System"]

    %% Data Flow
    Frontend -->|User Inputs, Requests| Backend
    Backend -->|Authenticate Users| Auth["🔐 Authentication"]
    Backend -->|Query, Store Data| Database["🗄️ Patient Database"]

    %% Security Controls
    Auth -.->|Encrypt Data in Transit| Security["🛡️ Security Layer"]
    Backend -.->|Audit Logs| Security