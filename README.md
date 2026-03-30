# 🚀 DevOps CI/CD Project

[![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)](https://python.org)
[![Flask](https://img.shields.io/badge/Flask-Web%20Framework-lightgrey?logo=flask)](https://flask.palletsprojects.com)
[![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?logo=docker)](https://docker.com)
[![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-CI%2FCD-2088FF?logo=githubactions)](https://github.com/features/actions)

A fully containerized Python Flask application with an automated CI/CD pipeline using GitHub Actions and Docker. This project demonstrates a real-world DevOps workflow — from code commit to automated build and deployment.

---

## 🏗️ Architecture Diagram

```
┌─────────────────────────────────────────────────────────────────────┐
│                        CI/CD PIPELINE                               │
│                                                                     │
│  👨‍💻 Developer                                                        │
│      │                                                              │
│      │  git push                                                    │
│      ▼                                                              │
│  ┌──────────────┐     trigger      ┌────────────────────────────┐  │
│  │   GitHub     │ ──────────────► │   GitHub Actions Workflow   │  │
│  │  Repository  │                 │                            │  │
│  └──────────────┘                 │  1️⃣  Checkout Code         │  │
│                                   │  2️⃣  Set up Python         │  │
│                                   │  3️⃣  Install Dependencies  │  │
│                                   │  4️⃣  Run Tests             │  │
│                                   │  5️⃣  Build Docker Image    │  │
│                                   │  6️⃣  Push to Registry      │  │
│                                   └────────────┬───────────────┘  │
│                                                │                   │
│                                                │  docker push      │
│                                                ▼                   │
│                                   ┌────────────────────┐          │
│                                   │   Docker Registry  │          │
│                                   │  (Docker Hub /     │          │
│                                   │   GitHub GHCR)     │          │
│                                   └────────────────────┘          │
└─────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────┐
│                      APPLICATION STACK                              │
│                                                                     │
│   🐳 Docker Container                                               │
│   ┌──────────────────────────────────────────────┐                 │
│   │                                              │                 │
│   │   🐍 Python Flask App  (port 5000)           │                 │
│   │   ┌──────────────────────────────────┐       │                 │
│   │   │  app.py                          │       │                 │
│   │   │  GET /  →  "Hello from DevOps!"  │       │                 │
│   │   └──────────────────────────────────┘       │                 │
│   │                                              │                 │
│   │   Base Image: python:3.x-slim               │                 │
│   │   Exposes: port 5000                         │                 │
│   └──────────────────────────────────────────────┘                 │
│                │                                                    │
│                │ HTTP Request                                       │
│                ▼                                                    │
│   🖥️  Client (curl / Browser)                                       │
│       → http://localhost:5000                                       │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 📁 Project Structure

```
devops-ci-cd-project/
├── .github/
│   └── workflows/
│       └── ci.yml          # GitHub Actions CI/CD pipeline
├── app.py                  # Flask application entry point
├── Dockerfile              # Container image definition
└── requirements.txt        # Python dependencies
```

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| Application | Python + Flask | REST API / Web server |
| Containerization | Docker | Package and run the app |
| CI/CD | GitHub Actions | Automate build, test, deploy |
| Runtime | Gunicorn / Flask dev | Serve the application |

---

## ⚡ Getting Started

### Run with Docker

```bash
# Clone the repository
git clone https://github.com/Aijazkhan123/devops-ci-cd-project.git
cd devops-ci-cd-project

# Build the Docker image
docker build -t devops-ci-cd-project .

# Run the container
docker run -p 5000:5000 devops-ci-cd-project
```

Visit: **http://localhost:5000**

### Run Locally (without Docker)

```bash
# Install dependencies
pip install -r requirements.txt

# Start the Flask app
python app.py
```

---

## ⚙️ CI/CD Pipeline

The GitHub Actions workflow (`.github/workflows/ci.yml`) triggers on every push to `master` and:

1. **Checks out** the repository code
2. **Sets up** Python environment
3. **Installs** dependencies from `requirements.txt`
4. **Runs** tests (if present)
5. **Builds** the Docker image
6. **Pushes** the image to a container registry

---

## 🧠 What I Learned

- Building and containerizing a Python Flask application with Docker
- Writing a complete CI/CD pipeline with GitHub Actions
- Understanding the full developer workflow: code → commit → build → deploy
- Managing dependencies with `requirements.txt` and Docker layers

---

## 🗺️ Planned Improvements

- [ ] Add unit tests with `pytest`
- [ ] Deploy to AWS EC2 / ECS or a Kubernetes cluster
- [ ] Add environment-specific config (dev / staging / prod)
- [ ] Add health check endpoint (`/health`)
- [ ] Integrate code quality linting (flake8, black)

---

## 📜 License

MIT License — feel free to fork and build on this!

---

`Python` · `Flask` · `Docker` · `GitHub Actions` · `CI/CD` · `DevOps`
