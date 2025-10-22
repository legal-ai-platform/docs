# Repository Guide – AI Legal Platform

This document lists all microservices and shared resources in the `legal-ai-platform` organization. Each component is developed and deployed independently.

---

## 🧩 Core Repositories

| Repository | Purpose | Owner | Tech Stack |
|-----------|--------|-------|-----------|
| [`deadline-service-api`](https://github.com/legal-ai-platform/deadline-service-api) | Manages legal contract deadlines, reminders, and time-critical obligations. | Abdul Rauf | Python, FastAPI, async |
| [`contract-analysis-engine`](https://github.com/legal-ai-platform/contract-analysis-engine) | AI-powered analysis of rental contracts: clause extraction, risk scoring, legality checks. | *TBD* | Python, NLP, LLMs, PyTorch/TensorFlow |
| [`web-frontend`](https://github.com/legal-ai-platform/web-frontend) | User dashboard for clients and lawyers (upload, view reports, manage mandates). | *TBD* | React, TypeScript |
---

## 📚 Shared Resources

| Repository | Purpose |
|----------|--------|
| [`docs`](https://github.com/legal-ai-platform/docs) | Central documentation: architecture, onboarding, API specs, decisions. |

---

## 🛠️ Contribution Rules

1. **One service = one repository**  
   No monoliths. Keep boundaries clear.

2. **All repos must include**:  
   - `README.md` (what it does + how to run)  
   - `Dockerfile`  
   - `.gitignore`  
   - OpenAPI spec (if it exposes an API)

3. **Use GitHub Issues + PRs**  
   All work tracked in the [Main Project Board](https://github.com/orgs/legal-ai-platform/projects/1).

4. **Never commit directly to `main`**  
   Use pull requests + 1 approval.

---

> 💡 **New developer?** Start with [`GETTING-STARTED.md`](./GETTING-STARTED.md).
