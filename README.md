# Flask Application - CI/CD Pipelines

A simple Flask web application with automated CI/CD pipelines using **Jenkins** and **GitHub Actions**.

## 📋 Table of Contents
- [Project Overview](#project-overview)
- [Application Features](#application-features)
- [CI/CD Pipelines](#cicd-pipelines)
  - [1. Jenkins Pipeline](#1-jenkins-pipeline)
  - [2. GitHub Actions Pipeline](#2-github-actions-pipeline)
- [Setup & Installation](#setup--installation)
- [Pipeline Triggers](#pipeline-triggers)
- [Notifications](#notifications)
- [Environment Secrets](#environment-secrets)
- [Deployment](#deployment)
- [Screenshots](#screenshots)

## Project Overview

This project demonstrates how to implement complete CI/CD pipelines for a Python Flask application using two popular tools:
- **Jenkins** (Self-hosted CI/CD)
- **GitHub Actions** (Cloud-native CI/CD)

---

## Application Features

- RESTful API built with Flask
- Unit testing with unittest/pytest
- Virtual environment support
- Easy deployment setup

---

## CI/CD Pipelines

### 1. Jenkins Pipeline

**File:** `Jenkinsfile`

**Stages:**
- **Checkout** – Pulls latest code
- **Build** – Creates virtual environment and installs dependencies
- **Test** – Runs unit tests
- **Deploy to Staging** – Deploys application (on successful build from `main` branch)

**Triggers:** Push to `main` branch

**Notifications:** Email notification on Success / Failure

### 2. GitHub Actions Pipeline

**File:** `.github/workflows/ci-cd.yml`

**Jobs:**
- Install Dependencies
- Run Tests
- Deploy to Staging (`staging` branch)
- Deploy to Production (on Release tag creation)

---

## Setup & Installation

### Prerequisites
- Python 3.9+
- Flask
- Git

### Local Setup

```bash
# Clone the repository
git clone <your-repo-url>
cd flask-app-cicd

# Create virtual environment
python -m venv venv
source venv/bin/activate    # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run the application
python run.py
