# Alpine Skiing Live Timing & Simulation System
*(Alp Disiplini Canlı Süre Takip ve Simülasyon Sistemi)*

A professional-grade, high-precision live timing and broadcast graphics system designed for Alpine Skiing (Slalom / Giant Slalom) disciplines. The project consists of a Python-based server implementing high-resolution physics and synchronization manager, paired with an elegant, responsive HTML5 client that serves both as a controller interface and a professional TV broadcast graphics overlay (Chroma Key green screen compatible).

---

## 🚀 Features / Özellikler

### 1. High-Precision Timing & Physics (Yüksek Hassasiyetli Zamanlama ve Fizik)
* **Centisecond Accuracy:** Handles timing data with centisecond (1/100s) precision, matching professional FIS timing equipment.
* **Low-Latency WebSockets:** Powered by a lightweight Python WebSocket server broadcasting live telemetry at 10 FPS to ensure smooth graphic transitions.
* **Dual-Run Support (1. ve 2. Tur Desteği):** Full event management for Alpine Skiing disciplines, including Run 1, Run 2, overall combined rankings, and DNF/DSQ tracking.

### 2. Client Controller UI (Yönetici Arayüzü)
* **Glassmorphic Light Theme:** Modern, clean, and high-contrast light-themed user interface designed for mobile phone screens to ensure physical buttons are easy to tap in snowy field conditions.
* **Racer Descriptions (Yarışmacı Açıklamaları):** Optional text fields to register notes (e.g., ski brand, club, history) that automatically show up on the TV pre-start screen.
* **Reference Timing (Referans Karşılaştırma):** One-click button to turn the last completed run into a comparison reference, displaying live relative advantage (+/-) on the track.
* **Mobile Responsive Layout:** Custom media queries tailored for iOS/iPhone web-viewers preventing viewport clipping and allowing full horizontal scroll support.

### 3. TV Broadcast Overlay Mode (TV Yayın/Grafik Modu)
* **Chroma Key Green Screen:** Fullscreen broadcast overlay with pure green background `#00ff00`, ready for OBS or ATEM hardware mixers.
* **Dynamic Pre-Start Card:** Bottom-right visual info box showing Bib Number, Racer Name, Run 1 details, Racer description, and relative leader gap.
* **Interactive Track Side-Bar:** Vertical progress bar on the right showing the athlete's current physical position on the run with color-coded speed zones.
* **Live TV Mini Leaderboard (Top 5 Pop-up):** A pop-up sliding list triggered upon racer finish showing top 5 current rankings. If the finishing racer is outside the top 5, it appends a custom 6th row with dynamic transition dots (`...`) to display their exact rank.
* **Sector Split Time Drawers:** Floating dynamic drawers presenting instant split times at Gate 1, Gate 2, and the Finish line.

### 4. Professional PDF Reporting (PDF Raporlama Çıktısı)
* Generates clean, ready-to-print PDF race protocols using `jsPDF` and `jspdf-autotable`.
* Allows inputting custom PDF document headers.
* Exports structured data tables including Run 1 Results, Run 2 Results, and Detailed Sector Analysis (Gate 1 & Gate 2 splits).

---

## 🛠️ Architecture & Technology Stack (Mimari ve Teknoloji)
[ Field Mobile App ] --> (HTTP/Socket Signals) --> [ Python WebSocket Server ] | (10 FPS Live Stream) v [ TV Overlay (OBS) ] <=========================== [ HTML5 Admin/TV Client ]


* **Backend:** Python 3.x, `asyncio`, `websockets` (running on port `8765`).
* **Frontend:** HTML5, CSS3 (Vanilla Glassmorphism), ES6 Javascript.
* **PDF Exporter:** `jsPDF` & `jspdf-autotable` integration.

---

## 📦 Installation & Running (Kurulum ve Çalıştırma)

### Prerequisites (Gereksinimler)
Make sure you have Python 3.x installed. Install the `websockets` package:
```bash
pip install websockets

1. Start the Server (Sunucuyu Başlatın)
Run the python script to boot up the telemetry manager:

python alpdisiplinibeta.py

2. Open the Client (İstemciyi Açın)
Simply double-click or open alpdisiplinibeta.html in any web browser (Chrome, Safari, Firefox).

To toggle the TV overlay, click the "TV MODU" button in the top right corner.
To exit TV mode, click the red "TV MODUNDAN ÇIK" button.
