# 🏓 Spanner Omni Pickleball Game
### Real-Time Agentic AI-Powered Pickleball Game and Tactical Analytics Platform

<p align="center">
  <img src="assets/pickleball-game.webp" alt="AI-Powered Pickleball Game Arena" width="100%">
</p>

## 🌟 Project Overview

- An interactive, AI-powered Pickleball Tactical Game Arena that combines real-time gameplay simulation with intelligent sports analytics using Google Cloud technologies. 
- Built with Python and Flask, the platform integrates Google Cloud Spanner Omni's relational and graph capabilities with Google Gemini to transform gameplay events into structured match intelligence.
- From simulating realistic rallies to analysing shot transitions and generating context-aware tactical recommendations, the project demonstrates how Agentic AI and graph-based data engineering can bring intelligence to interactive sports applications.

---

## 🎮 Features

- **Animated Visual Court Arena:** 2.5D visual pickleball court with animated playable characters (You vs OmniBot-3000) and realistic 60 FPS wiffle ball trajectory physics.
- **Spanner Omni Graph Engine:** Each rally shot and counter-response logs shot nodes (`s1:Shot`, `s2:Shot`) and transition relationships (`[:TRANSITIONED_TO]`) directly in Spanner.
- **Agentic AI Tactical Coach:** Powered by Google Gemini with live Spanner telemetry grounding for intelligent match analysis and tactical recommendations.
- **Web Audio API Effects:** Pure synthesized paddle hit pops, court bounce thuds, and speedup swooshes.
- **Interactive Control Deck:** Choose from Kitchen Soft Dinks, 3rd-Shot Drops, Shoulder Speedups, and Offensive Lobs with spin control.

---

## 🛠️ Technology Stack

- **Programming Language:** Python
- **Backend Framework:** Flask
- **Database:** Google Cloud Spanner Omni
- **AI Model:** Google Gemini
- **Graph Technology:** Graph GQL and graph-based telemetry
- **Frontend:** HTML, CSS, JavaScript
- **Browser APIs:** Web Audio API
- **Containerization:** Docker

---

## 🚀 Quick Start

### 1. Install Dependencies

Clone the repository:

```bash
git clone https://github.com/kunalkapade01/Building-a-Real-Time-AI-Powered-Pickleball-Game.git

cd Building-a-Real-Time-AI-Powered-Pickleball-Game
```

Install Python dependencies:

```bash
pip install -r requirements.txt
```

### 2. Configure Environment Variables

Create a `.env` file in the project root directory using the provided `.env.example` file.

Add your required configuration:

```env
GOOGLE_API_KEY=your_google_gemini_api_key
```

Replace the placeholder with your own API key.

**Important:** Never commit your actual `.env` file, API keys, or service account credentials to GitHub.

### 3. Set Up Google Cloud Spanner Omni

Create a persistent Docker volume:

```bash
docker volume create spanner_omni_data
```

Pull the Spanner Omni image:

```bash
docker pull us-docker.pkg.dev/spanner-omni/images/spanner-omni:2026.r2.1-beta
```

Run Spanner Omni in single-server mode:

```bash
docker run -d --name spanner-omni \
  -p 9010:9010 -p 9020:9020 \
  -v spanner_omni_data:/spanner \
  us-docker.pkg.dev/spanner-omni/images/spanner-omni:2026.r2.1-beta \
  start-single-server
```

Verify that the container is running:

```bash
docker ps
```

### 4. Run the Application

Start the Flask application:

```bash
python app.py
```

Once the application starts, open the local application URL displayed in your terminal to access the interactive Pickleball Tactical Game Arena.

---

## 📂 Project Structure

```text
Building-a-Real-Time-AI-Powered-Pickleball-Game/
│
├── app.py                  # Flask backend, Spanner transactions & Gemini AI
├── requirements.txt        # Python dependencies
├── Dockerfile              # Container definition
├── start.sh                # Automated bootstrap script
├── .env.example            # Environment variable template
├── .gitignore              # Excludes secrets and unnecessary files
├── README.md               # Project documentation
│
└── templates/
    └── index.html          # 2.5D visual animated court arena
```

---

## 🧠 Core Implementation Highlights

- **Real-Time Game Simulation:** Interactive gameplay with animated characters, shot selection, ball trajectories, and rally mechanics.
- **Graph-Based Game Intelligence:** Models shot events as graph nodes and rally transitions as relationships using Spanner Omni.
- **AI-Powered Tactical Analysis:** Integrates Google Gemini with gameplay telemetry to generate contextual match insights and tactical coaching.
- **Relational and Graph Data Management:** Combines structured game records with graph-based relationships to support gameplay analysis.
- **Interactive User Experience:** Integrates visual animations, audio effects, and player controls into a browser-based game arena.

---

## 🎯 Project Objective

To explore the integration of Agentic AI, graph-based data modelling, and cloud-native database technologies in an interactive sports application. The project demonstrates how real-time gameplay events can be transformed into meaningful data insights and AI-assisted tactical recommendations.

---

## 👨‍💻 Author

**Kunal Kapade**

- GitHub: [@kunalkapade01](https://github.com/kunalkapade01)

---

*Built with Python, Google Cloud Spanner Omni, and Google Gemini.*
