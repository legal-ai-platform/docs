```md
# Developer Setup Guide

## Prerequisites
- Python 3.11+
- Node.js 20+
- Docker & Docker Compose
- PostgreSQL (or use Docker)
- Access to AI Engine (local mock available)

## Local Development

### 1. Clone Repos
```bash
gh repo clone ai-law-firm/frontend
gh repo clone ai-law-firm/backend
gh repo clone ai-law-firm/ai-engine  # or use mock for MVP
```

### 2. Backend (FastAPI)
```bash
cd backend
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
cp .env.example .env
docker-compose up -d  # starts PostgreSQL, Redis
uvicorn app.main:app --reload
```

### 3. Frontend (React)
```bash
cd frontend
npm install
cp .env.example .env.local
npm run dev
```

### 4. AI Engine (for Basheer’s MVP)
Use the `/analyze` mock endpoint during frontend dev:
```json
// GET /mock-analysis
{ "risk_score": 0.78, "summary": "...", "clauses": [...], "rent_comparison": {...} }
```

> 💡 Tip: Use `ngrok` or GitHub Codespaces for shared testing.
```

---

### 📄 4. `apis/ai-engine-contract.md`

```md
# AI Engine – Contract Analysis API Contract

## Input
- `file`: PDF, DOCX, or JPG (≤10 MB)
- `contract_type`: optional hint (e.g., `"rental"`)

## Output (JSON)
```json
{
  "risk_score": 0.78,
  "summary": "The contract contains...",
  "clauses": [
    {
      "text": "Tenant must repaint walls",
      "rating": "illegal",
      "source": "OGH 3 Ob 20/19x",
      "recommendation": "Remove or replace with compliant wording."
    }
  ],
  "rent_comparison": {
    "actual_rent": 850,
    "average_rent": 670,
    "status": "overpriced",
    "percentage_above": 27
  }
}
```

> ✅ Ratings: `"legal"`, `"questionable"`, `"illegal"`  
> 🌐 Sources must link to **RIS**, **OGH**, or **Arbeiterkammer**
```

---

### ✅ Next Steps for You

1. **Create these files** in your `ai-law-firm/docs` repo.
2. **Enable GitHub Pages** (Settings → Pages → Deploy from `/(root)` or `/docs`).
3. **Link this repo** in all other repos’ READMEs (e.g., “See full docs at [ai-law-firm/docs](https://github.com/ai-law-firm/docs)”).
4. **Invite team members** to contribute (e.g., AI team adds model details, legal adds clause sources).

Would you like me to:
- Generate a **Mermaid diagram** for `system-overview.md`?
- Provide a **sample OpenAPI spec** for the backend?
- Create a **Markdown template for new contract types**?

Just say the word!
