# Autonomous Line-Following Robot with PI Control

**Embedded Control · Robotics · Sensors & Actuators · Control Systems**  
Curtin University — Mechatronics Design Project (MXEN3000)

---

## 🧠 Project Overview
Designed and built an **autonomous line-following robot** capable of accurately tracking a predefined path using **optical sensing** and a **Proportional–Integral (PI) control algorithm**.

The project focused on **robust mechanical design**, **sensor reliability**, and **control-system tuning**, integrating hardware and software into a stable, responsive robotic system.

---

## 🎯 System Objectives
- Accurately follow a black-and-white track using optical sensors  
- Maintain stability during sharp turns and speed changes  
- Minimize oscillations and overcorrection  
- Enable real-time monitoring and tuning through a custom GUI  

---

## 🏗️ Vehicle Architecture Overview
The robot is a compact, maneuverable platform built for precision control and stability.

<img src="images/full_robot.jpg" width="600">

### Key Structural Features
- **Wide chassis** for improved stability  
- **Low center of gravity** achieved by mounting components 6 mm above the base  
- **Caterpillar tracks** for high traction and sharp directional changes  
- **Lightweight construction** to reduce power consumption  

---

## 🛠️ Mechanical & Electrical Design

### Optical Sensing System
- **Sensors:** Dual opto-sensors (IR emitter + LDR)
- **Mounting height:** ~8 mm above surface
- **Spacing:** 3.5 cm between sensors
- **Function:** Distinguish white (on-track) vs black (off-track)

<img src="images/sensors.jpg" width="400">

This configuration provided reliable binary readings while minimizing ambient light interference.

---

### Drive System
- **Motors:** Two DC motors (0.09 kg each)
- **Coupling:** Direct 1:1 coupling (no gearbox)
- **Drive:** Caterpillar tracks for enhanced grip and maneuverability

<img src="images/drive_system.jpg" width="400">

Motors were rear-mounted to avoid interference and ensure balanced weight distribution.

---

### Power & Electronics
- **Battery:** 3 × 3.7 V Li-ion cells (11.1 V total)
- **Main PCB includes:**
  - 555 timers
  - DACs
  - Operational amplifiers
  - Comparators
- **Controller:** Arduino Nano

<img src="images/pcb.jpg" width="400">

All components were selected to ensure **TTL compatibility (5 V logic)**, enabling reliable sensor–controller communication without additional voltage conversion.

---

## 🔄 Control System Design

### Control Strategy Selection
Three control strategies were evaluated:

| Controller | Outcome |
|----------|--------|
| Bang-Bang | Simple but caused jitter, oscillations, and oversteering |
| PID | High performance but too complex to tune within project scope |
| **PI (Chosen)** | Best balance between smooth control and simplicity |

The **PI controller** provided stable tracking while reducing oscillations and overshoot.

---

## 📐 PI Control Algorithm

### Sensor Interpretation
- Sensor value < 240 → **White (on-track)** → `1`
- Sensor value ≥ 240 → **Black (off-track)** → `0`

### Error Calculation

