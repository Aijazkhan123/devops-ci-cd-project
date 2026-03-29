# DevOps CI/CD Project

[![Python](https://img.shields.io/badge/Python-3.9-blue?logo=python)](https://python.org) [![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?logo=docker)](https://docker.com) [![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-CI%2FCD-2088FF?logo=github-actions)](https://github.com/features/actions) [![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> A production-style CI/CD pipeline that automatically builds, containerizes, and validates a Python Flask application on every code push — zero manual deployment steps.

---

## Pipeline Overview

<svg width="900" height="340" viewBox="0 0 900 340" xmlns="http://www.w3.org/2000/svg" font-family="'Segoe UI', system-ui, sans-serif">
  <defs>
    <marker id="arr" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto-start-reverse">
      <path d="M1 1L9 5L1 9" fill="none" stroke="#64748b" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
    </marker>
    <filter id="shadow" x="-10%" y="-10%" width="120%" height="130%">
      <feDropShadow dx="0" dy="2" stdDeviation="3" flood-color="#0001" flood-opacity="1"/>
    </filter>
  </defs>

  <!-- Background -->
  <rect width="900" height="340" fill="#f8fafc" rx="16"/>

  <!-- Title -->
  <text x="450" y="38" text-anchor="middle" font-size="15" font-weight="700" fill="#0f172a" letter-spacing="-0.3">CI/CD Pipeline — devops-ci-cd-project</text>
  <text x="450" y="58" text-anchor="middle" font-size="11" fill="#94a3b8">Automated on every push to master</text>

  <!-- Step 1: Developer -->
  <g filter="url(#shadow)">
    <rect x="40" y="110" width="130" height="90" rx="12" fill="#fff" stroke="#e2e8f0" stroke-width="1.5"/>
  </g>
  <rect x="40" y="110" width="130" height="8" rx="4" fill="#6366f1"/>
  <rect x="40" y="114" width="130" height="4" fill="#6366f1"/>
  <text x="105" y="150" text-anchor="middle" font-size="22">💻</text>
  <text x="105" y="172" text-anchor="middle" font-size="12" font-weight="600" fill="#1e293b">Developer</text>
  <text x="105" y="188" text-anchor="middle" font-size="10" fill="#64748b">git push master</text>

  <!-- Arrow 1 -->
  <line x1="172" y1="155" x2="208" y2="155" stroke="#64748b" stroke-width="1.5" marker-end="url(#arr)" stroke-dasharray="4 3"/>
  <text x="190" y="147" text-anchor="middle" font-size="9" fill="#94a3b8">triggers</text>

  <!-- Step 2: GitHub Actions -->
  <g filter="url(#shadow)">
    <rect x="210" y="110" width="130" height="90" rx="12" fill="#fff" stroke="#e2e8f0" stroke-width="1.5"/>
  </g>
  <rect x="210" y="110" width="130" height="8" rx="4" fill="#2088ff"/>
  <rect x="210" y="114" width="130" height="4" fill="#2088ff"/>
  <text x="275" y="150" text-anchor="middle" font-size="22">⚙️</text>
  <text x="275" y="172" text-anchor="middle" font-size="12" font-weight="600" fill="#1e293b">GitHub Actions</text>
  <text x="275" y="188" text-anchor="middle" font-size="10" fill="#64748b">Workflow triggered</text>

  <!-- Arrow 2 -->
  <line x1="342" y1="155" x2="378" y2="155" stroke="#64748b" stroke-width="1.5" marker-end="url(#arr)" stroke-dasharray="4 3"/>
  <text x="360" y="147" text-anchor="middle" font-size="9" fill="#94a3b8">builds</text>

  <!-- Step 3: Docker Build -->
  <g filter="url(#shadow)">
    <rect x="380" y="110" width="130" height="90" rx="12" fill="#fff" stroke="#e2e8f0" stroke-width="1.5"/>
  </g>
  <rect x="380" y="110" width="130" height="8" rx="4" fill="#2496ed"/>
  <rect x="380" y="114" width="130" height="4" fill="#2496ed"/>
  <text x="445" y="150" text-anchor="middle" font-size="22">🐳</text>
  <text x="445" y="172" text-anchor="middle" font-size="12" font-weight="600" fill="#1e293b">Docker Build</text>
  <text x="445" y="188" text-anchor="middle" font-size="10" fill="#64748b">Image created</text>

  <!-- Arrow 3 -->
  <line x1="512" y1="155" x2="548" y2="155" stroke="#64748b" stroke-width="1.5" marker-end="url(#arr)" stroke-dasharray="4 3"/>
  <text x="530" y="147" text-anchor="middle" font-size="9" fill="#94a3b8">runs</text>

  <!-- Step 4: Container -->
  <g filter="url(#shadow)">
    <rect x="550" y="110" width="130" height="90" rx="12" fill="#fff" stroke="#e2e8f0" stroke-width="1.5"/>
  </g>
  <rect x="550" y="110" width="130" height="8" rx="4" fill="#0ea5e9"/>
  <rect x="550" y="114" width="130" height="4" fill="#0ea5e9"/>
  <text x="615" y="150" text-anchor="middle" font-size="22">📦</text>
  <text x="615" y="172" text-anchor="middle" font-size="12" font-weight="600" fill="#1e293b">Container Run</text>
  <text x="615" y="188" text-anchor="middle" font-size="10" fill="#64748b">App started</text>

  <!-- Arrow 4 -->
  <line x1="682" y1="155" x2="718" y2="155" stroke="#64748b" stroke-width="1.5" marker-end="url(#arr)" stroke-dasharray="4 3"/>
  <text x="700" y="147" text-anchor="middle" font-size="9" fill="#94a3b8">validates</text>

  <!-- Step 5: Health Check -->
  <g filter="url(#shadow)">
    <rect x="720" y="110" width="130" height="90" rx="12" fill="#fff" stroke="#e2e8f0" stroke-width="1.5"/>
  </g>
  <rect x="720" y="110" width="130" height="8" rx="4" fill="#22c55e"/>
  <rect x="720" y="114" width="130" height="4" fill="#22c55e"/>
  <text x="785" y="150" text-anchor="middle" font-size="22">✅</text>
  <text x="785" y="172" text-anchor="middle" font-size="12" font-weight="600" fill="#1e293b">Pipeline Passed</text>
  <text x="785" y="188" text-anchor="middle" font-size="10" fill="#64748b">Health verified</text>

  <!-- Bottom legend -->
  <rect x="40" y="240" width="820" height="70" rx="10" fill="#f1f5f9" stroke="#e2e8f0" stroke-width="1"/>
  <text x="60" y="262" font-size="11" font-weight="700" fill="#475569">Stack:</text>
  <rect x="100" y="250" width="8" height="8" rx="2" fill="#6366f1"/>
  <text x="114" y="260" font-size="11" fill="#475569">Python 3.9</text>
  <rect x="195" y="250" width="8" height="8" rx="2" fill="#f97316"/>
  <text x="209" y="260" font-size="11" fill="#475569">Flask</text>
  <rect x="260" y="250" width="8" height="8" rx="2" fill="#2496ed"/>
  <text x="274" y="260" font-size="11" fill="#475569">Docker</text>
  <rect x="335" y="250" width="8" height="8" rx="2" fill="#2088ff"/>
  <text x="349" y="260" font-size="11" fill="#475569">GitHub Actions</text>

  <text x="60" y="295" font-size="10" fill="#94a3b8">Trigger: push to master  •  Base image: python:3.9-slim  •  Port: 5000  •  Zero manual steps</text>
</svg>

---

## Project Structure

<svg width="900" height="320" viewBox="0 0 900 320" xmlns="http://www.w3.org/2000/svg" font-family="'Segoe UI', system-ui, sans-serif">
  <defs>
    <filter id="shadow" x="-10%" y="-10%" width="120%" height="130%">
      <feDropShadow dx="0" dy="2" stdDeviation="3" flood-color="#0001"/>
    </filter>
  </defs>

  <rect width="900" height="320" fill="#0f172a" rx="16"/>

  <!-- Title -->
  <text x="450" y="38" text-anchor="middle" font-size="15" font-weight="700" fill="#f1f5f9" letter-spacing="-0.3">Project Structure — devops-ci-cd-project</text>

  <!-- File tree panel -->
  <rect x="40" y="60" width="280" height="230" rx="10" fill="#1e293b" stroke="#334155" stroke-width="1"/>
  <text x="60" y="88" font-size="12" font-weight="700" fill="#94a3b8" font-family="monospace">devops-ci-cd-project/</text>

  <!-- Tree lines and files -->
  <line x1="72" y1="100" x2="72" y2="220" stroke="#334155" stroke-width="1"/>

  <line x1="72" y1="112" x2="88" y2="112" stroke="#334155" stroke-width="1"/>
  <text x="94" y="117" font-size="11" fill="#7dd3fc" font-family="monospace">📁 .github/</text>

  <line x1="100" y1="124" x2="100" y2="148" stroke="#334155" stroke-width="1"/>
  <line x1="100" y1="136" x2="116" y2="136" stroke="#334155" stroke-width="1"/>
  <text x="122" y="141" font-size="11" fill="#94a3b8" font-family="monospace">📁 workflows/</text>
  <line x1="128" y1="148" x2="128" y2="160" stroke="#334155" stroke-width="1"/>
  <line x1="128" y1="160" x2="144" y2="160" stroke="#334155" stroke-width="1"/>
  <text x="150" y="165" font-size="11" fill="#fbbf24" font-family="monospace">ci.yml</text>

  <line x1="72" y1="178" x2="88" y2="178" stroke="#334155" stroke-width="1"/>
  <text x="94" y="183" font-size="11" fill="#86efac" font-family="monospace">🐍 app.py</text>

  <line x1="72" y1="200" x2="88" y2="200" stroke="#334155" stroke-width="1"/>
  <text x="94" y="205" font-size="11" fill="#7dd3fc" font-family="monospace">🐳 Dockerfile</text>

  <line x1="72" y1="222" x2="88" y2="222" stroke="#334155" stroke-width="1"/>
  <text x="94" y="227" font-size="11" fill="#c4b5fd" font-family="monospace">📄 requirements.txt</text>

  <!-- File detail cards -->
  <!-- ci.yml -->
  <rect x="360" y="60" width="240" height="75" rx="8" fill="#1e293b" stroke="#fbbf24" stroke-width="1.5"/>
  <text x="376" y="82" font-size="11" font-weight="700" fill="#fbbf24">⚙️ .github/workflows/ci.yml</text>
  <text x="376" y="98" font-size="10" fill="#94a3b8">GitHub Actions pipeline definition.</text>
  <text x="376" y="112" font-size="10" fill="#94a3b8">Runs on every push to master.</text>
  <text x="376" y="126" font-size="10" fill="#64748b">Trigger → Build → Run → Validate</text>

  <!-- app.py -->
  <rect x="360" y="150" width="240" height="75" rx="8" fill="#1e293b" stroke="#86efac" stroke-width="1.5"/>
  <text x="376" y="172" font-size="11" font-weight="700" fill="#86efac">🐍 app.py</text>
  <text x="376" y="188" font-size="10" fill="#94a3b8">Flask web application. Serves HTTP</text>
  <text x="376" y="202" font-size="10" fill="#94a3b8">endpoint on port 5000.</text>
  <text x="376" y="216" font-size="10" fill="#64748b">GET /  →  "Hello from DevOps!"</text>

  <!-- Dockerfile -->
  <rect x="620" y="60" width="240" height="75" rx="8" fill="#1e293b" stroke="#7dd3fc" stroke-width="1.5"/>
  <text x="636" y="82" font-size="11" font-weight="700" fill="#7dd3fc">🐳 Dockerfile</text>
  <text x="636" y="98" font-size="10" fill="#94a3b8">Builds the container image using</text>
  <text x="636" y="112" font-size="10" fill="#94a3b8">python:3.9-slim base image.</text>
  <text x="636" y="126" font-size="10" fill="#64748b">Installs deps → copies app → runs</text>

  <!-- requirements.txt -->
  <rect x="620" y="150" width="240" height="75" rx="8" fill="#1e293b" stroke="#c4b5fd" stroke-width="1.5"/>
  <text x="636" y="172" font-size="11" font-weight="700" fill="#c4b5fd">📄 requirements.txt</text>
  <text x="636" y="188" font-size="10" fill="#94a3b8">Pinned Python dependencies for</text>
  <text x="636" y="202" font-size="10" fill="#94a3b8">reproducible installs.</text>
  <text x="636" y="216" font-size="10" fill="#64748b">flask, werkzeug, ...</text>

  <!-- Bottom bar -->
  <rect x="40" y="268" width="820" height="32" rx="8" fill="#1e293b" stroke="#334155" stroke-width="1"/>
  <text x="450" y="288" text-anchor="middle" font-size="10" fill="#64748b">Python 3.9  ·  Flask  ·  Docker  ·  GitHub Actions  ·  Port 5000</text>
</svg>

---

## What I Built

I designed and implemented an end-to-end DevOps pipeline for a Python web application. The pipeline triggers automatically on every push to `master`, builds a Docker image, and validates the running container — mirroring how modern engineering teams ship software continuously and reliably.

This project demonstrates my ability to:
- Build and manage CI/CD pipelines with **GitHub Actions**
- Write production-ready **Dockerfiles** using slim base images
- Automate the full build → containerize → validate workflow
- Follow industry-standard project structure and dependency management

---

## Tech Stack

| Technology | Role |
|---|---|
| Python 3.9 | Application runtime |
| Flask | Lightweight web framework |
| Docker | Container build and runtime |
| GitHub Actions | CI/CD pipeline automation |

---

## How the Pipeline Works

Every push to `master` triggers the following automated workflow:

```
Git Push → GitHub Actions Triggered
         → Docker Image Built
         → Container Started
         → App Health Validated
         → Pipeline Passes ✅
```

The Dockerfile uses `python:3.9-slim` — a minimal base image chosen to reduce attack surface and keep image size small, which is best practice for production containers.

---

## File Structure

```
devops-ci-cd-project/
├── .github/
│   └── workflows/        # GitHub Actions CI/CD pipeline definition
├── app.py                # Flask application
├── Dockerfile            # Container build
└── requirements.txt      # Pinned Python dependencies
```

---

## Run It Locally

**With Docker:**
```bash
git clone https://github.com/Aijazkhan123/devops-ci-cd-project.git
cd devops-ci-cd-project
docker build -t devops-ci-cd-app .
docker run -p 5000:5000 devops-ci-cd-app
```
Open **http://localhost:5000**

**Without Docker:**
```bash
pip install -r requirements.txt
python app.py
```

---

## Skills Demonstrated

`CI/CD` · `Docker` · `GitHub Actions` · `Python` · `Flask` · `Pipeline Automation` · `Container Build Optimization`
