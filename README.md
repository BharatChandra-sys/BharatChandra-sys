# Bharat Chandra

CSE student at GITAM University (2027). I build systems that work in real environments — not demos, not notebooks, not university assignments.

The common thread across everything I build: connecting an intelligence layer to something physical or operational. Rocket telemetry. Underwater autonomy. Clinical AI. Production e-commerce. The code either works under real constraints, or it doesn't work.

📬 bc833498@gmail.com &nbsp;·&nbsp; [LinkedIn](https://linkedin.com/in/bodapati-bharat-chandra-4b1b58290) &nbsp;·&nbsp; [GitHub](https://github.com/chandu1234678)

---

## Stack

**Languages** — Python, JavaScript, SQL, Java, C  
**Backend** — FastAPI, REST API design, JWT auth, WebSockets, async I/O  
**ML / AI** — PyTorch, Scikit-Learn, TF-IDF, CNNs, Grad-CAM, SHAP, MLflow, DVC  
**Autonomous Systems** — ROS2, Kalman filtering, sensor fusion, real-time telemetry  
**Frontend** — React, TypeScript, Vite, Chrome Extension APIs  
**Infrastructure** — PostgreSQL, MongoDB, Docker, Prometheus, Grafana, Cloudinary

---

## Projects

### CAN-7USAT Ground Control Station
`Python · FastAPI · WebSocket · Kalman Filter · PostgreSQL · React · TypeScript` — **2026**

Real-time ground control station for the **IN-SPACe Model Rocketry Competition 2026**, built for GITAM University's CAN-7USAT team targeting 1000 m AGL.

The backend decodes 46-byte binary telemetry packets from a Teensy 4.1 flight computer transmitted over a 900 MHz XBee radio link, runs Kalman filter sensor fusion, maintains a 6-state flight state machine, and broadcasts live data to a React dashboard over WebSocket.

**Numbers that matter:**
- End-to-end latency: **< 5 ms** (target was 15 ms)
- Packet decode time: **0.5 ms** (target was 2 ms)
- WebSocket broadcast: **1 ms** (target was 5 ms)
- Packet loss: **0%** across all 23/23 passing tests

**Packet structure:** 46 bytes — sync byte, timestamp, flight state, altitude, velocity, quaternion (W/X/Y/Z), GPS lat/long, XOR checksum  
**State machine:** `PRE-FLIGHT → BOOST → COAST → APOGEE → DESCENT → LANDED`  
**Stack detail:** FastAPI + Uvicorn + asyncpg + NumPy/SciPy (Kalman) · React 18 + TypeScript + Zustand + uPlot (real-time charts) + Three.js

> The challenge wasn't writing the code — it was writing code that works once, correctly, on launch day, with a rocket already on the pad.

[→ Repository](https://github.com/chandu1234678/CAN-7USAT-Ground-Control-Backend)

---

### AUVBrain — Autonomous Underwater Vehicle Control System
`Python · FastAPI · ROS2 · Docker · asyncio` — **2026**

Full autonomous control stack for an underwater vehicle. No internet, no margin for error. Every component had to work offline and degrade gracefully.

The system runs a deterministic `observe → decide → act` agent loop with 4-DOF thruster control and a safety monitor that enforces hard limits on depth, battery, temperature, and obstacle proximity before any decision executes.

- Offline LLM decision engine (llama.cpp / OpenAI-compatible API) with rules-based fallback when the model is unavailable or slow
- Agent loop p95 latency: **≈ 0.84 ms**
- Append-only JSONL telemetry logging for full mission replay and post-mission analysis
- Structured telemetry covers every state transition, decision, and sensor reading

> Designing the fallback logic was harder than building the main path. What does the vehicle do when the LLM times out at 20 m depth? That question drove the architecture.

[→ Repository](https://github.com/chandu1234678/AUVBrain)

---

### MedVision AI — Explainable AI System for Diabetic Ulcer Detection
`PyTorch · FastAPI · Grad-CAM · SHAP · Docker · MLflow · DVC · Prometheus · Grafana` — **2025–2026**

Started at the **AI Day Hackathon (GITAM × Kodryx AI, March 2026)**. Extended into a production-deployed clinical decision-support platform.

The system combines medical image analysis and structured clinical data (age, BMI, diabetes duration) to estimate ulcer risk — and critically, it shows *why* it made that call.

- Custom CNN in PyTorch for image classification
- Grad-CAM heatmaps highlight which image regions the model attends to
- SHAP values quantify how each clinical feature influenced the prediction
- Patient timeline tracking for ulcer progression monitoring
- Full MLOps stack: MLflow experiment tracking, DVC dataset versioning, Prometheus metrics, Grafana dashboards
- 5 production health-check endpoints (`/health`, `/health/ping`, `/health/ready`, `/health/live`, `/health/status`)
- JWT auth, RBAC, Cloudinary image storage, Docker Compose
- **Live:** [diabetic-ulcer-ai-system.vercel.app](https://diabetic-ulcer-ai-system.vercel.app)

> Black-box predictions are a liability in clinical settings. The explainability layer isn't a nice-to-have — it's the entire point. A clinician needs to understand, challenge, and override the system.

[→ Repository](https://github.com/chandu1234678/diabetic-ulcer-ai-system)

---

### Fake News Analyzer
`FastAPI · Chrome Extension · TF-IDF · Logistic Regression · LLM reasoning` — **2025–2026**

Started at **HackXplore (IEEE-SSIT Student Chapter, VJIT, April 2026)**. A browser extension that scores news content for credibility as you browse — one click, instant result.

- Logistic Regression on 10,000+ labeled samples, **90% validation accuracy** with TF-IDF vectorization
- Model loaded into memory at startup for sub-second response
- LLM reasoning layer generates contextual verdict explanations beyond the raw confidence score
- Chrome extension extracts DOM content and transmits it to the FastAPI backend via CORS-configured endpoints

> The interesting design problem wasn't the model — it was latency. The pipeline had to feel instant. That forced early decisions about model loading, memory layout, and what work happens at startup vs. at request time.

[→ Extension](https://github.com/chandu1234678/fake-news-analyzer) &nbsp;·&nbsp; [→ Backend](https://github.com/chandu1234678/fake-news-backend)

---

### Hospital Management Platform
`FastAPI · PostgreSQL · SQLAlchemy · React · JWT · RBAC` — **2025**

Full-stack platform for real hospital workflows. The goal was to model the domain correctly, not just build CRUD endpoints.

- Relational PostgreSQL schema with ORM mapping — patient records, appointments, inventory, all designed around how the data actually relates
- Strict RBAC: Admin, Doctor, and Receptionist roles hitting entirely separate data partitions — enforced at the query level, not just in route handlers
- ACID-compliant transaction blocks for anything that touches multiple tables
- Decoupled React frontend and FastAPI backend, clean REST boundaries throughout

> The hard part was the domain model. If the schema is wrong, no amount of application logic fixes it. I spent more time on the database design than on the API.

[→ Repository](https://github.com/chandu1234678/hospital-management-platform)

---

### Vijetha Digital — E-Commerce Backend
`FastAPI · PostgreSQL · JWT · Razorpay` — **2024–Present** · *Production, live*

Backend for a real printing business. Not a demo. In use.

- 15+ REST endpoints, JWT auth, bcrypt hashing, multi-role access (User / Admin / Business)
- Razorpay payment integration
- 6-state order lifecycle (`pending → confirmed → in-production → ready → dispatched → delivered`) across 10 relational tables with ACID transactions

[→ Repository](https://github.com/chandu1234678/vijetha-digital-backend)

---

## Experience

**AI Intern — SmartED Innovations** &nbsp;·&nbsp; Feb 2026 – Present  
Designing ML workflows in Python/Scikit-Learn, building FastAPI integrations for model inference pipelines

**AI/ML Intern — Elevate Labs** &nbsp;·&nbsp; Apr 2026 – May 2026  
Applied ML: preprocessing, training, evaluation, deployment-oriented backend integrations

---

## What I'm focused on right now

MLOps in practice — model serving, versioning, monitoring, drift detection. Advanced backend patterns — connection pooling, async task queues, caching. Distributed systems basics. Deeper XAI for domains where the explanation matters as much as the prediction.

---

*I learn fastest when something real is at stake. Most of what I know came from a deadline, a broken system, or a constraint that ruled out the obvious solution.*
