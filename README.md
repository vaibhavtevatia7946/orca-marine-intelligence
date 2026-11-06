m# 🐋 ORCA Marine Intelligence

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Vercel%20Production-00d4ff?style=for-the-badge&logo=vercel)](https://orca-marine-intelligence-two.vercel.app)
[![GitHub license](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)
[![Frontend](https://img.shields.io/badge/Frontend-React%20%7C%20Vite%20%7C%20MapLibre-61DAFB?style=for-the-badge&logo=react)](https://orca-marine-intelligence-two.vercel.app)
[![Backend](https://img.shields.io/badge/Backend-FastAPI%20%7C%20LangGraph-009688?style=for-the-badge&logo=fastapi)](https://github.com/vaibhavtevatia7946/orca-marine-intelligence)
[![PWA](https://img.shields.io/badge/PWA-Installable%20%26%20Offline%20Ready-5A0FC8?style=for-the-badge&logo=pwa)](https://orca-marine-intelligence-two.vercel.app)

> **Autonomous AI Marine Intelligence & Coastal Navigation Observatory**  
> Developed & maintained by **[Vaibhav Tevatia](https://github.com/vaibhavtevatia7946)**

ORCA is an agentic AI maritime decision-support platform designed for coastal fishermen, maritime vessels, and ocean researchers across the Indian Ocean coastline. It correlates real-time satellite Earth Observation, ocean forecasts, tide harmonics, and international maritime boundaries into natural-language safety advisories and interactive GIS maps.

---

## 🌟 Key Features

* **🗺️ Interactive Maritime GIS Map:** Powered by MapLibre GL with Carto Voyager basemap switcher, displaying EEZ, Marine Protected Areas (MPAs), and International Maritime Boundary Lines (IMBL).
* **🎣 Potential Fishing Zones (PFZ):** Geospatial telemetry showing optimal chlorophyll and Sea Surface Temperature (SST) zones.
* **⚠️ Coastal Hazard & Cyclone Tracking:** High wave alerts, wind velocity tracking, barometric pressure anomaly detection, and safe routing corridors.
* **🗣️ Multilingual & Hands-Free Voice:** Speech synthesis and voice input in 11 Indian languages (Hindi, Tamil, Telugu, Malayalam, Gujarati, Bengali, Marathi, etc.).
* **📱 Mobile-First PWA (Progressive Web App):** Offline caching via Service Workers and installable on Android, iOS, and Desktop.
* **🤖 Swarm AI Decision Matrix:** Multi-agent routing powered by LangGraph, Groq LPU, and Google Gemini with safety threshold overrides.
* **📚 Maritime Knowledge & Quiz Mode:** Comprehensive quiz and knowledge testing module covering navigation rules, safety protocols, and Indian maritime law.

---

## 🏗️ Architecture

```
┌──────────────────────────────────────────────────────────────────┐
│                   React + Vite PWA Frontend                      │
│  ┌────────────┐  ┌─────────────────────────────────────────────┐ │
│  │ Chat Panel  │  │           MapLibre GL Map                   │ │
│  │ Voice I/O   │  │  • PFZ zones (green)                       │ │
│  │ Language     │  │  • Hazard zones (red)                      │ │
│  │ Agent Trace  │  │  • Safe routes (blue)                      │ │
│  │ PWA Offline  │  │  • SST heatmap (orange)                     │ │
│  │             │  │  • IMBL boundary (purple)                   │ │
│  └──────┬──────┘  │  • Mobile Responsive Tabs                   │ │
│         │         └─────────────────────────────────────────────┘ │
└─────────┼────────────────────────────────────────────────────────┘
          │ POST /api/chat
          ▼
┌──────────────────────────────────────────────────────────────────┐
│                    FastAPI Backend                                │
│  ┌──────────────┐  ┌──────────────────────────────────┐          │
│  │ Translation   │  │ LangGraph Multi-Agent Swarm       │          │
│  │ Middleware     │→ │  ┌─────────┐ ┌─────────────────┐ │         │
│  │ (Indic/Edge) │  │  │ Router  │→│ Tool Dispatcher  │ │         │
│  └──────────────┘  │  └─────────┘ └────────┬────────┘ │         │
│                    │               ┌───────┴────────┐  │         │
│                    │    ┌──────────┤  Specialists    │  │         │
│                    │    ▼          ▼         ▼       ▼  │         │
│                    │  Data     Safety     PFZ     Route │         │
│                    │  Agent    Agent     Agent    Agent  │         │
│                    └────────────────────────────────────┘         │
│                    ┌──────────────────────────────────┐          │
│                    │     Telemetry Data Layer         │          │
│                    │  SST · Chlorophyll · Open-Meteo · │          │
│                    │  INCOIS Bulletins · Users SQLite │          │
│                    └──────────────────────────────────┘          │
└──────────────────────────────────────────────────────────────────┘
```

---

## 🚀 Quick Start

### 1. Clone the Repository
```bash
git clone https://github.com/vaibhavtevatia7946/orca-marine-intelligence.git
cd orca-marine-intelligence
```

### 2. Frontend Setup
```bash
cd frontend
npm install
npm run dev
```

### 3. Backend Setup
```bash
cd backend
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
uvicorn app:app --reload --port 8000
```

---

## ☁️ Deployment

### Frontend (Vercel)
Deploy with the Vercel CLI or link your GitHub repository directly to Vercel:
```bash
vercel --prod
```

### Backend (Render)
Deploy the backend on Render with 1 click using the included `render.yaml`:

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/vaibhavtevatia7946/orca-marine-intelligence)

---

## 📄 License
This project is open source and available under the [MIT License](LICENSE).
