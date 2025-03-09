# Cybersecurity Incident Tracker - Architecture Model

## 1. System Overview
The **Cybersecurity Incident Tracker** follows a **three-tier architecture**:
- **Frontend:** Web-based user interface.
- **Backend:** API server for handling incidents.
- **Database:** Stores all security events.

## 2. Architectural Diagrams

### **Context Diagram**
```mermaid
graph TD;
    A[Security Analyst] -->|Reports & tracks incidents| B[Cybersecurity Incident Tracker]
    C[SIEM System] -->|Sends security alerts| B
graph TD;
    subgraph Cybersecurity Incident Tracker
        B1[Web Application (React.js / Angular)]
        B2[Backend API (Node.js / Django)]
        B3[Incident Database (PostgreSQL / MongoDB)]
    end

    A[Security Analyst] -->|Logs in & manages incidents| B1
    B1 -->|Sends/receives data| B2
    B2 -->|Stores & retrieves logs| B3
graph TD;
    subgraph Backend API
        C1[Incident Service - Manages incidents]
        C2[User Authentication - Handles login & roles]
        C3[Incident Reporting - Generates audit reports]
    end

    C1 -->|Stores data| D[Incident Database]
    C2 -->|Manages users| D
    C3 -->|Retrieves reports| D


```
