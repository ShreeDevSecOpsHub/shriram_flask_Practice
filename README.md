# Flask Practice App with CI/CD

Simple Flask web application with automated testing and deployment.

## CI/CD Pipelines Implemented

### 1. Jenkins Pipeline (Jenkinsfile)
- Triggers on push to `jenkins` branch
- Stages: Build → Test → Deploy (to same Jenkins server as staging)
- Uses `pytest` for testing
- Sends email notification on success/failure

### 2. GitHub Actions Workflow
- Two deployment paths:
  - `staging` branch → Deploy to staging
  - Tagged release (e.g., v1.0.0) → Deploy to production
- Secrets used for secure deployment

## Local Setup
```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python app.py
