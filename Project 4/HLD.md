```mermaid
flowchart TD;
    %% External Users & Systems
    Patients["👤 Patients"] -->|Web/Mobile Access| Frontend["🌐 Web App (React)"]
    HealthcareProviders["🏥 Providers"] -->|Manage Patients| Frontend
    ThirdParty["🔗 Third-Party Services"] -->|API Requests| Backend["⚙️ Backend (Node.js)"]

    %% System Infrastructure
    Frontend -->|REST API Calls| Backend
    Backend -->|Authenticate & Manage Users| Auth["🔐 Authentication (Cognito, SSO)"]
    Backend -->|Store & Retrieve Patient Data| Database["🗄️ Database (MariaDB)"]
    Backend -->|File Storage| S3["☁️ AWS S3 Storage"]

    %% Security & CI/CD Pipeline
    Auth -.->|MFA, Access Control| Security["🛡️ Security Layer"]
    Backend -.->|Monitoring & Logging| Security
    Backend -->|Automated Deployments| CI_CD["🚀 CI/CD (GitHub Actions)"]