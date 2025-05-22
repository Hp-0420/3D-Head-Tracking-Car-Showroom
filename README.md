# 🧠🎮 AR/VR Head Tracking System using Python & Unity

![AR/VR](https://img.shields.io/badge/Project-Type%3A%20AR--VR-blueviolet?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Made With](https://img.shields.io/badge/Made%20With-Python%20%26%20Unity-yellow?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-orange?style=for-the-badge)

---

## 📝 Project Description

I successfully built an **AR/VR head-tracking application** that connects **Python (for face tracking)** with **Unity (for immersive 3D visualization)**. This project enables users to control a 3D camera using their head movement captured through a regular webcam — no expensive hardware needed!

> 📹 **Video Inspiration**: [YouTube Tutorial](https://youtu.be/m-CHTkMW_ho?feature=shared)  
> 🔄 I built this project step-by-step and added my own improvements and understanding to complete the entire workflow.

---

## 🎯 Objective

Create a real-time **interactive head-controlled camera** in Unity that mimics user head movements using a webcam feed processed in Python.

---

## 🛠️ Tech Stack

| Tool       | Description                                      |
|------------|--------------------------------------------------|
| 🐍 Python  | Captures head movement using `cvzone` + `MediaPipe` |
| 🧠 MediaPipe | Detects face and tracks center point            |
| 📡 UDP     | Transmits coordinates from Python → Unity        |
| 🎮 Unity   | 3D scene rendering, camera control                |
| 🧾 C#      | UDP listener + camera transform logic             |

---

## 📸 Key Features

- Real-time head position tracking via webcam
- Seamless communication between Python and Unity via UDP
- Unity camera follows head movement (left, right, up, down)
- Smoothing algorithm to reduce jitter
- Perfect for interactive VR showrooms or simulations

---

## 🧠 How It Works

### 🐍 Python Side

- Uses `cvzone` + `MediaPipe` to detect face from webcam
- Calculates **center (X, Y)** coordinates of the face
- Sends data continuously over **UDP** using Python `socket`

### 📡 Communication

- Uses UDP (User Datagram Protocol) for real-time transmission
- Python sends data to `localhost:port` where Unity listens

### 🎮 Unity Side

- Listens for UDP messages using C# `UdpClient`
- Parses incoming string data to extract X and Y
- Applies values to update the **Main Camera’s position and rotation**
- Includes smoothing technique using averaging buffer

---

## 🔄 Data Flow Diagram

```mermaid
graph TD
    A[Webcam Input] --> B[Python + MediaPipe]
    B --> C[Extract X, Y Center]
    C --> D[Send via UDP Socket]
    D --> E[Unity UDP Receiver]
    E --> F[Parse X, Y Data]
    F --> G[Update Camera Transform]
    G --> H[Interactive 3D Scene]
````

---

## 🧩 Project Structure

```
📁 HeadTracking-Unity-Python
├── Python/
│   ├── head_tracking.py
│   ├── requirements.txt
├── Unity/
│   ├── Assets/
│   │   ├── Scripts/
│   │   │   ├── udpReceiver.cs
│   │   │   ├── cameraControl.cs
├── README.md
```

---

## ✨ Enhancements I Made

* 🧹 Implemented **smoothing filter** using a moving average
* 💡 Added **lighting and realistic assets** in Unity showroom
* 🎛️ Tuned **camera movement sensitivity** for cinematic control
* ⚙️ Modular Python code for reusability and scalability

---

## 🚀 How to Run

### ✅ Python Setup

```bash
pip install cvzone opencv-python mediapipe
python head_tracking.py
```

### ✅ Unity Setup

1. Open Unity and import the project
2. Add the C# scripts (`udpReceiver.cs`, `cameraControl.cs`) to an empty GameObject
3. Attach Main Camera to follow input from the script
4. Hit **Play** and test with webcam

---

## 🎥 Preview

> **Head movement → Camera movement!**

![Demo](https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExNjBweGEzc3M0eXY5Zms2aGIwNTUzN2E2ZjBob2hvZWUyZWRhYXB1MSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/usBjEZ7Kx1WubhHwCs/giphy.gif)

---

## 💡 Applications

* 🔧 VR/AR prototyping
* 🛍️ Virtual showroom or customer engagement kiosk
* 🧠 Eye/head-controlled user interfaces
* 🎓 Educational simulations and gaming

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙌 Acknowledgements

* Inspired by the awesome [YouTube tutorial](https://youtu.be/m-CHTkMW_ho?feature=shared)
* Built with ❤️ and expanded using my own logic, Unity experience, and Python skills

---

> ✨ If you found this useful, feel free to ⭐ the repo and share your feedback!
