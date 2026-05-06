# Bharat Chandra

CSE student at GITAM University, Hyderabad. I build backend systems and ML-powered applications — the kind that run in real environments, not just in notebooks.

My focus is on the gap between a trained model and a working product. That means APIs, inference pipelines, telemetry systems, and production architecture. I learn by shipping things.

📬 bc833498@gmail.com · [LinkedIn](https://linkedin.com/in/bodapati-bharat-chandra-4b1b58290) · [GitHub](https://github.com/chandu1234678)

---

## What I Work With

**Languages** — Python, JavaScript, SQL, Java, C  
**Backend** — FastAPI, REST API design, JWT auth, async I/O, WebSockets  
**ML / AI** — PyTorch, Scikit-Learn, TF-IDF, CNNs, Grad-CAM, SHAP, MLflow  
**Autonomous Systems** — ROS2, Kalman filtering, real-time telemetry, sensor fusion  
**Frontend** — React, Chrome Extension APIs  
**Infrastructure** — PostgreSQL, MongoDB, Docker, Git

---

## Projects

### 🚀 CAN-7USAT Ground Control Station
`Python · FastAPI · WebSocket · Kalman Filter · PostgreSQL · React` · **2026**

Built for the **IN-SPACe Model Rocketry Competition 2026**. A real-time telemetry backend that decodes 46-byte binary flight packets from a Teensy 4.1 flight computer transmitted over a 900 MHz XBee radio link.

- End-to-end latency under 5 ms, 0% packet loss across all 23 test runs
- Kalman filter fusing barometer and accelerometer readings for clean altitude estimation
- 6-state flight state machine: `PRE-FLIGHT → BOOST → COAST → APOGEE → DESCENT → LANDED`
- Live 10 Hz WebSocket broadcast to a React dashboard

> This one had real stakes — actual rocket, actual competition. The backend had to work on launch day with no room to debug mid-flight.

[→ Repository](https://github.com/chandu1234678/CAN-7USAT-Ground-Control-Backend)

---

### 🤖 AUVBrain — Autonomous Underwater Vehicle Control System
`Python · FastAPI · ROS2 · Docker · asyncio` · **2026**

Autonomous control stack for an underwater vehicle. Implements a deterministic `observe → decide → act` agent loop with 4-DOF thruster control.

- Safety monitor enforcing hard limits on depth, battery, temperature, and obstacle proximity
- Offline LLM decision engine (llama.cpp / OpenAI-compatible) with rules-based fallback when LLM is unavailable
- Agent loop p95 response time ≈ 0.84 ms
- Append-only JSONL telemetry logging for full mission replay

> The constraint was no internet on the vehicle. Everything had to run offline and fail gracefully. That shaped every design decision.

[→ Repository](https://github.com/chandu1234678/AUVBrain)

---

### 🔬 Explainable AI System for Diabetic Ulcer Detection
`PyTorch · FastAPI · Grad-CAM · SHAP · Docker · MLflow` · **2025–2026**

Started at the **AI Day Hackathon (GITAM, March 2026)**, then extended into a production-grade clinical decision-support API.

- Custom CNN trained in PyTorch for medical image classification
- Grad-CAM heatmaps show which image regions the model uses; SHAP values explain tabular feature impact
- FastAPI inference backend containerised with Docker, MLflow experiment tracking, JWT auth, RBAC, and 5 health-check endpoints

> The point wasn't accuracy alone — it was making the model's reasoning visible to clinicians who need to trust and challenge it.

[→ Repository](https://github.com/chandu1234678/diabetic-ulcer-ai-system)

---

### 📰 Fake News Analyzer
`FastAPI · Chrome Extension · TF-IDF · Logistic Regression · LLM` · **2025–2026**

Started at **HackXplore (IEEE-SSIT, VJIT, April 2026)**. A Chrome extension that scores news content for credibility as you browse.

- Logistic Regression on 10,000+ labeled samples, 90% validation accuracy with TF-IDF vectorization
- Model loaded into memory at startup — sub-second scoring
- FastAPI backend with an LLM reasoning layer for contextual verdict generation beyond the raw score

> The challenge was making the whole pipeline invisible. You highlight text, click once, get an answer. That UX constraint drove the backend design.

[→ Extension](https://github.com/chandu1234678/fake-news-analyzer) · [→ Backend](https://github.com/chandu1234678/fake-news-backend)

---

### 🏥 Hospital Management Platform
`FastAPI · PostgreSQL · SQLAlchemy · React · JWT · RBAC` · **2025**

Full-stack system for real hospital workflows — not a demo app.

- Relational PostgreSQL schema with ORM mapping for patient records, appointments, and inventory
- Strict RBAC across Admin, Doctor, and Receptionist roles with ACID-compliant transaction blocks
- Decoupled React frontend and FastAPI backend with clean API boundaries

> The interesting problem here was domain modeling — figuring out how hospital data actually relates and then making the system enforce those rules at the database level.

[→ Repository](https://github.com/chandu1234678/hospital-management-platform)

---

### 🛒 Vijetha Digital — E-Commerce Backend
`FastAPI · PostgreSQL · JWT · Razorpay` · **2024–Present**

Production backend for a real printing business. Live, in use.

- 15+ REST endpoints with JWT auth, bcrypt hashing, and multi-role access (User / Admin / Business)
- Razorpay payment integration
- 6-state order lifecycle across 10 relational tables with ACID-compliant transaction handling

[→ Repository](https://github.com/chandu1234678/vijetha-digital-backend)

---

## Experience

**AI Intern — SmartED Innovations** · Feb 2026 – Present  
ML workflows in Python/Scikit-Learn, FastAPI integrations for model inference pipelines

**AI/ML Intern — Elevate Labs** · Apr 2026 – May 2026  
Applied ML tasks: preprocessing, model training, evaluation, deployment-oriented backend work

---

## Currently Working On

- MLOps: model serving, versioning, and monitoring in production
- Advanced backend architecture and database query optimization
- Distributed systems fundamentals
- Deeper XAI techniques for high-stakes domains

---

*I prefer building over reading about building. Most of what I know came from running into a real problem and having to solve it.*
