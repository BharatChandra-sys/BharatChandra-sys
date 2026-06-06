<div align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=26&duration=3000&pause=1000&color=6E40C9&center=true&vCenter=true&width=600&lines=Bharat+Chandra;Backend+%26+AI+Systems+Engineer;Rocket+Telemetry.+Clinical+AI.+AUV+Control." alt="Typing SVG" />
</div>

<div align="center">

[![LinkedIn](https://img.shields.io/badge/-Bharat_Chandra-blue?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/bodapati-bharat-chandra-4b1b58290)
[![Gmail](https://img.shields.io/badge/-bc833498@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:bc833498@gmail.com)
[![Live Demo](https://img.shields.io/badge/-MedVision_AI_Live-00C7B7?style=flat-square&logo=vercel&logoColor=white)](https://diabetic-ulcer-ai-system.vercel.app)

</div>

---

CSE @ GITAM University Hyderabad · Interning @ BHEL · Building systems that work under real constraints — not demos, not notebooks.

The thread: an intelligence layer connected to something that has consequences. A rocket on a launch pad. An underwater vehicle at 20 m depth with no internet. A clinician who needs to understand and override an AI prediction.

---

## Stack

<div align="center">

![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/-FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![PyTorch](https://img.shields.io/badge/-PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![React](https://img.shields.io/badge/-React-61DAFB?style=flat-square&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-336791?style=flat-square&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![WebSockets](https://img.shields.io/badge/-WebSockets-010101?style=flat-square&logo=socketdotio&logoColor=white)
![ROS2](https://img.shields.io/badge/-ROS2-22314E?style=flat-square&logo=ros&logoColor=white)
![MLflow](https://img.shields.io/badge/-MLflow-0194E2?style=flat-square&logo=mlflow&logoColor=white)

</div>

---

## Projects

### CAN-7USAT — Real-Time Rocket Ground Control
> IN-SPACe Model Rocketry Competition 2026 · targeting 1000 m AGL

Decodes 46-byte binary telemetry from a Teensy 4.1 over 900 MHz XBee, runs Kalman filter sensor fusion, drives a 6-state flight state machine, streams live to a React dashboard over WebSocket.

| Metric | Target | Achieved |
|--------|--------|----------|
| End-to-end latency | 15 ms | < 5 ms |
| Packet decode | 2 ms | 0.5 ms |
| WebSocket broadcast | 5 ms | 1 ms |
| Packet loss | — | 0% across 23 tests |

`Python` `FastAPI` `WebSocket` `Kalman Filter` `React` `TypeScript` → [Repository](https://github.com/chandu1234678/CAN-7USAT-Ground-Control-Backend)

---

### AUVBrain — Autonomous Underwater Vehicle Control
> No internet. No margin for error. p95 agent loop: 0.84 ms

Deterministic observe → decide → act loop with 4-DOF thruster control. Offline LLM (llama.cpp) with rules-based fallback. What does the vehicle do when the LLM times out at 20 m depth? That question drove the architecture.

`Python` `FastAPI` `ROS2` `Docker` `llama.cpp` → [Repository](https://github.com/chandu1234678/AUVBrain)

---

### MedVision AI — Clinical Explainable AI · [Live](https://diabetic-ulcer-ai-system.vercel.app)
> AI Day Hackathon — GITAM x Kodryx AI, March 2026

Diabetic ulcer detection with Grad-CAM heatmaps and SHAP values. Black-box predictions are a liability in clinical settings — the explainability layer isn't a feature, it's the point.

`PyTorch` `Grad-CAM` `SHAP` `FastAPI` `MLflow` `Docker` `Prometheus` → [Repository](https://github.com/chandu1234678/diabetic-ulcer-ai-system)

---

### Fake News Analyzer · 90% accuracy
> HackXplore — IEEE-SSIT, VJIT, April 2026

Chrome extension → FastAPI → TF-IDF + Logistic Regression on 10k+ samples + LLM reasoning layer. Sub-second pipeline.

`FastAPI` `Chrome Extension` `TF-IDF` `Scikit-Learn` → [Extension](https://github.com/chandu1234678/fake-news-analyzer) · [Backend](https://github.com/chandu1234678/fake-news-backend)

---

### Hospital Management Platform
Full-stack. RBAC enforced at query level. ACID transactions. Schema designed before a single route was written.

`FastAPI` `PostgreSQL` `React` `JWT` → [Repository](https://github.com/chandu1234678/hospital-management-platform)

---

### Vijetha Digital · Production. Live. Real orders.
Backend for a real printing business. 6-state order lifecycle. Razorpay integration.

`FastAPI` `PostgreSQL` `Razorpay` → [Repository](https://github.com/chandu1234678/vijetha-digital-backend)

---

## GitHub Stats

<div align="center">
  <img height="160" src="https://github-readme-stats.vercel.app/api?username=chandu1234678&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" />
  <img height="160" src="https://github-readme-stats.vercel.app/api/top-langs/?username=chandu1234678&layout=compact&theme=tokyonight&hide_border=true" />
</div>

<div align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=chandu1234678&theme=tokyonight&hide_border=true" />
</div>

---

## Experience

| Company | Role | Period |
|---------|------|--------|
| BHEL (PSU) | Software Intern | Ongoing |
| SmartED Innovations | AI Intern | Feb 2026 – Present |
| Elevate Labs | AI/ML Intern | Apr – May 2026 |

---

<div align="center">

*I learn fastest when something real is at stake.*  
*Most of what I know came from a deadline, a broken system, or a constraint that ruled out the obvious solution.*

</div>
