# Web-Fire-Detection
Real-time web-based fire detection system using live camera feed, color analysis, and alert mechanisms. 


A **real-time camera-based fire detection system** built using **HTML, CSS, and JavaScript**.  
This project detects fire-like colors from a live camera feed, highlights the detected region, and triggers **visual, audio, and animation alerts**.

Optimized for **mobile phones, tablets, desktops**, and works smoothly even via **Termux**.

---

## 🚀 Features

- 📷 Live camera feed using browser camera
- 🔁 Flip between front & back cameras
- 🔥 Real-time fire color detection
- 🟥 Red glowing bounding box around detected fire
- 🚨 Visual alert: **“FIRE DETECTED!”**
- 🔊 Audio alert on detection
- 😨 Panic image with shaking animation
- 🌐 No backend required (runs fully in browser)

---

## 🛠️ Technologies Used

- **HTML5** – Structure
- **CSS3** – Styling, animations, responsiveness
- **JavaScript (Vanilla)** – Logic & camera handling
- **Canvas API** – Pixel processing & drawing
- **MediaDevices API** – Camera access

---

## ⚙️ How It Works (Detailed)

### 1️⃣ Camera Access
- Uses `navigator.mediaDevices.getUserMedia()`
- Supports both **front (user)** and **rear (environment)** cameras
- Flip camera button provided for mobile devices

### 2️⃣ Frame Processing
- Video frames are copied into a **low-resolution offscreen canvas**
- This improves performance and reduces CPU usage on phones

### 3️⃣ Fire Detection Logic
Each pixel is analyzed using RGB values.

A pixel is considered **fire-like** if:
- 🔴 Red value is high
- 🟢 Green is moderate
- 🔵 Blue is low
- Red value is greater than green

```js
r > 190 && g > 100 && b < 90 && r > g
---
├── index.html
├── mk.png              # Panic image
├── fire_extinguish.mp3 # Alert sound
└── README.md
