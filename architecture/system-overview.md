# System Overview

The AI Law Firm platform follows a **domain-driven microservices architecture**, with clear separation between frontend, core backend, AI processing, and integration layers.

## 🗺️ High-Level Components

| Component | Responsibility | Tech |
|--------|----------------|------|
| **Frontend** | React dashboard (Matter View, Editor, Deadlines) | React, TypeScript |
| **API Gateway** | Auth, routing, rate limiting | FastAPI / Traefik |
| **Core Services** | Matters, Documents, Tasks, Forms | FastAPI, PostgreSQL |
| **AI Engine** | Contract analysis, deadline extraction, RAG | Python, LLMs, OCR |
| **Integrations** | Outlook, Advokat, ERV, Firmenbuch | REST, OAuth, Webhooks |
| **Storage** | Docs, versions, audit logs | S3 + PostgreSQL + TimescaleDB |

## 🔁 Data Flow Example: Rental Contract Upload
1. User uploads PDF → Frontend → Backend (`/upload`)
2. Backend stores file → triggers async job to **AI Engine**
3. AI Engine returns structured JSON → stored in **Documents service**
4. Frontend polls → displays risk score, clauses, rent comparison
5. Deadlines auto-synced to **Deadline service** → pushed to Outlook

See also: [AI Modules](ai-modules.md), [Deadline AI Architecture](deadline-ai-architecture.md)
