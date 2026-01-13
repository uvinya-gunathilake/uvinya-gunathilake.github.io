# Autonomous Line-Following Robot with PI Control

**Embedded Control · Robotics · Sensors & Actuators · Control Systems**  
Curtin University — Mechatronics Design Project (MXEN3000)

---

## 🧠 Project Overview
This project involved the design, construction, and control of an **autonomous line-following robot** capable of accurately tracking a predefined path using **optical sensors and a Proportional–Integral (PI) control algorithm**.

The robot integrates **mechanical design**, **sensor systems**, **analog and digital electronics**, **embedded programming**, and **GUI-based monitoring** to achieve smooth, stable, and reliable line-following performance.

---

## 📸 Final Vehicle
<img src="images/final_vehicle.jpg" width="650">

The robot is a compact, maneuverable platform designed to follow a white track surrounded by black regions with high precision.

---

## 🏗️ Vehicle Design Overview

### Textual Description
The robot uses a **tracked locomotion system** consisting of two wide plastic caterpillar tracks mounted on wheels, providing excellent traction and stability across varying surfaces. Two opto-sensors are mounted at the front of the vehicle to detect contrast between the track and surrounding surface.

Sensor outputs are processed through:
- A **GUI-based control system**
- An **Arduino Nano**
- An onboard **analog control PCB**

This chain controls motor speed and direction to maintain accurate path tracking.

The motors (0.09 kg each) are rear-mounted to avoid mechanical interference and are directly coupled to the wheels for efficient torque transmission. A custom PCB mounted on top houses:
- 555 timers  
- DACs  
- Operational amplifiers  
- Comparators  

Power is supplied by a **3-cell Li-ion battery (11.1 V)** housed at the rear.

---

## 📐 Physical Design Considerations
- Lightweight materials minimize power consumption
- Low center of gravity achieved by mounting PCB components as low as **6 mm**
- Sensors mounted **8 mm above ground** for optimal IR reflection
- Sensor spacing of **3.5 cm** ensures accurate detection
- Wide chassis improves stability and reduces wobble
- Caterpillar tracks allow sharp turns without loss of grip

---

## ⚙️ System Architecture & Functional Parameters
Key design parameters considered:
- Surface contrast sensitivity (black vs white)
- Motor speed (RPM), torque (N·m), and weight
- PWM-based motor control
- Battery voltage, current draw, and runtime
- Sensor response latency
- Path deviation and correction time
- Maximum vehicle weight

---

## 🛠️ Key Technical Challenges & Solutions

### Hardware Challenges
| Challenge | Solution |
|--------|---------|
Sensor spacing issues | Reduced gap and recalibrated height for accurate detection |
Loose electronic connections | Secured components to prevent signal loss |
Unstable chassis during turns | Lowered center of gravity and used lightweight materials |

### Electronics Challenges
| Challenge | Solution |
|--------|---------|
Signal noise and interference | Implemented push-pull signal conditioning |
Arduino–PCB communication failure | Rewritten serial communication code |
Bang-bang control instability | Replaced with PI controller |

### Software Challenges
| Challenge | Solution |
|--------|---------|
PI controller implementation | Learned error tracking using queues |
Controller tuning | Iterative testing and parameter adjustment |

---

## 🎯 Anticipated Vehicle Performance
- Smooth traversal of curved tracks
- Accurate on-track/off-track detection
- Sharp turns with minimal deviation
- Minor performance variations due to friction and environment
- Improved robustness through tuning

---

## 📊 Key Performance Indicators (KPIs)

| KPI | Metric |
|----|------|
Speed | m/s, total track completion time |
Tracking accuracy | Path deviation (cm) |
Response speed | Correction latency (ms) |
Turning precision | Angular error (degrees) |
Motor control | PWM accuracy (%) |
Sensor sensitivity | Binary accuracy (%) |
Data transmission | GUI response time (ms) |

---

## 🧩 Key Design Decisions

### Control System Selection
- Bang-bang: simple but unstable
- PID: powerful but complex
- **PI controller chosen** for balance between stability and simplicity

### Sensor Placement
- Mounted 8 mm above ground
- Spaced 3.5 cm apart
- Ensures reliable binary detection

### GUI Design
- Real-time sensor and motor monitoring
- Simplifies tuning and debugging

### TTL Compatibility
- Sensors and Arduino Nano operate at 5 V logic
- No voltage conversion required
- Reliable digital interfacing

### Motor & Drive Configuration
- Direct 1:1 motor-to-wheel coupling
- Caterpillar tracks for traction
- Optimized wheelbase width

---

## 🔄 Control Algorithm (PI Controller)

### Sensor Interpretation
- Sensor value > 240 → Black (off-track) → 0
- Sensor value < 240 → White (on-track) → 1

### Error Calculation
Error = Right Sensor − Left Sensor

- Error = 0 → On track
- Error = +1 → Drift left
- Error = −1 → Drift right

### PI Control
P = Kp × Current Error
I = Ki × Σ(Past Errors)
Response = P + I


The last **10 error values** are stored to smooth control actions.

### Motor Control Logic
- Positive response → right turn
- Negative response → left turn
- PWM duty cycles adjusted independently

---

## 🔌 Communication Protocol

### Serial Data Packet (5 Bytes)
| Byte | Description |
|----|------------|
Byte 0 | Start byte (255) |
Byte 1 | Command byte |
Byte 2 | Sensor / Motor data |
Byte 3 | Sensor / Motor data |
Byte 4 | Checksum |

Checksum ensures packet integrity.

---

## 🖥️ GUI Features
- Start/Stop control
- Real-time sensor readings
- PWM duty cycle display
- Error notifications
- Color-coded sensor panels
- Graphical motor speed indicators
- Visual cart position tracking

---

## ❌ Mistakes & Fixes

### ADC Resolution Error
- Arduino ADC is 10-bit
- Initial readings unstable
- Fixed by scaling to 8-bit (`value / 4`)

### Serial Communication Failure
- GUI commands not reaching PCB
- Rewritten serial handling code
- Fully restored communication

---

## 📈 Results Summary

| Aspect | Outcome |
|----|--------|
Sensor stability | Improved after calibration |
Motor balance | Minor imbalance at sharp turns |
Tracking accuracy | < 50 mm deviation |
PWM accuracy | ±5% |
Overall performance | Stable, reliable line following |

---

## 📚 Lessons Learned
- Optical sensing depends heavily on calibration
- Ambient light introduces noise
- Bang-bang control causes oscillations
- PI control offers smooth, stable tracking
- PID provides better performance but requires complex tuning
- Trade-offs between simplicity, precision, and stability are critical in control design

---

## 🚀 Conclusion
This project demonstrates a complete **mechatronics system**, integrating sensing, actuation, control algorithms, electronics, and software. The PI-controlled line-following robot achieved reliable performance while highlighting the importance of calibration, controller selection, and system-level design thinking.

