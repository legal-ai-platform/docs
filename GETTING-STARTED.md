# Getting Started – Developer Onboarding

Follow these steps to set up and run any service locally.

## 1. Clone the Repository You’re Working On

Example for the deadline service:
```bash
git clone https://github.com/legal-ai-platform/deadline-service-api.git
cd deadline-service-api
```

## 2. Install Dependencies

Each service lists its dependencies in one of these files:
- `requirements.txt` (Python)
- `package.json` (Node.js)

Example (Python):
```bash
pip install -r requirements.txt
```

## 3. Run with Docker (Recommended)

Every service includes a `Dockerfile`. Build and run:
```bash
docker build -t service-name .
docker run -p 8000:8000 service-name
```
Replace `service-name` with the actual service (e.g., `deadline-service`).

> ✅ All services expose HTTP on port `8000` by default.

## 4. Run Without Docker (Optional)

If you prefer local execution:
- **Python services**:  
  ```bash
  python app/main.py
  ```
> Ensure you have the correct Python version (3.10+) and virtual environment.

## 5. Access API Docs

For FastAPI-based services (like `deadline-service-api`), visit:  
http://localhost:8000/docs

## Required Files in Every Service Repo

Make sure your repo includes these files:
- `README.md`
- `Dockerfile`
- `.gitignore`
- `requirements.txt` or `package.json`
- `app/main.py` (or equivalent entry point)

If any are missing, add them before pushing code.
