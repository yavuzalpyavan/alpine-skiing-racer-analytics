# 🎿 Real-Time Alpine Skiing Race Analytics & Physics Simulation Framework

A high-performance, full-stack broadcasting and telemetry analytics framework designed for Alpine Skiing races (FIS World Cup disciplines). The system features an asynchronous **Python** backend paired with a real-time, responsive **JavaScript/HTML5/CSS3** television-style graphics (TV Mode) and referee control interface.

---

## 🚀 Key Engineering & Architectural Features

### ⚡ 1. Network Latency Compensation Algorithm
Wireless transmissions on local networks often introduce latency jitter (ranging between 250ms–300ms). To ensure millisecond-accurate live timing charts, the client-side JavaScript engine implements a custom **Latency Compensation** algorithm. It continuously cross-references high-resolution local client timers with server-stamped state logs, dynamically eliminating network transmission lag from the active live difference calculations.

### 📊 2. Continuous Memory-Slicing Streak/Combo Trend Algorithm
The core analytics layer runs a real-time mathematical slicing loop to monitor athlete trajectory efficiency. By assessing average delta changes over continuous sectors, the algorithm dynamically calculates speed trend shifts (gain/loss momentum) and instantly projects temporary performance brackets onto the broadcast interface.

### 🔌 3. High-Efficiency Asynchronous Communication
Built entirely on top of Python's **`asyncio`** and **`websockets`** infrastructure. Rather than forcing the server to constantly push heavy render loads at 100 FPS, the architecture offloads fluid rendering to the client-side via browser-native `requestAnimationFrame` hooks. This optimization reduced server compute frequency to a lean 10 FPS (0.1s interval sleep cycle), saving over 90% of server network overhead while keeping UI frame transitions entirely smooth.

### 📁 4. Automated Analytical Exporting
Includes modular data aggregation structures that compile deep-dive statistics per runner (Sector splits, historical gate differences, overall ranks, and individual run parameters) with automated, localized, Excel-compatible CSV report generation hooks.

---

## 🛠️ Tech Stack & Dependencies

* **Backend:** Python 3.x, `asyncio`, `websockets`, `json`, `time`
* **Frontend:** Vanilla JavaScript (ES6+), HTML5, CSS3 (Custom Glassmorphism & Adaptive Layouts)
* **Architecture:** Event-Driven Bidirectional Client-Server Sync / Stateful Ledger

---

## 💻 Installation & Quick Start

1. **Clone the Repository:**
   ```bash
   git clone [https://github.com/YOUR_GITHUB_USERNAME/alpine-skiing-racer-analytics.git](https://github.com/YOUR_GITHUB_USERNAME/alpine-skiing-racer-analytics.git)
   cd alpine-skiing-racer-analytics

Run the WebSocket Server:

Bash

python server/alpdisiplinibeta.py

Launch the Interface:

Open client/alpdisiplinibeta.html in any modern web browser. Click the 📺 TV MODU button to activate the automated overlay system.

📊 Live System Previews
TV Mode Graphics: Operates on an automated Chroma Key green background for direct broadcasting integration. Features dynamic pre-start cards, live target calculations, and high-performance scrolling split times.

Automation Settings: Configurable micro-gate turning triggers allowing absolute layout synchronization with the actual physical course boundaries.
