# Automated Crazy Machine Controlled by Finite State Machine (FSM)

**Mechatronics Systems Integration · Sensors · Actuators · Embedded Control**  
Curtin University — Mechatronics Engineering (Group Project)

---

## 🧠 Project Overview
Designed and implemented an automated **Rube Goldberg–style “Crazy Machine”** that transports a steel ball through multiple mechanical stages using coordinated **sensing, actuation, and finite state machine (FSM) control**.

The system was engineered as a **Moore-model FSM**, ensuring deterministic, repeatable behavior and robust integration between mechanical mechanisms and embedded control logic.

---

## 🛠 System Description
The machine consists of multiple mechanically and electrically actuated stages, including:
- Entrance slide with light-based ball detection
- Merry-Go-Round (stepper motor)
- Maze with force-based detection
- Ferris wheel lifting mechanism
- Linear piston actuator
- Elevator with electromagnet
- Servo-controlled bridge and exit slide

Each stage is triggered by **sensor feedback** and controlled through well-defined FSM states.

---

## 🔄 Control Architecture (FSM-Based Design)
The entire machine is governed by a **Moore finite state machine**, where outputs depend solely on the current state, improving predictability and safety.

### State Sequence Summary
- **Reset (I):** System initializes and returns all mechanisms to default positions  
- **Wait (A):** Ball detected at entrance using LDR  
- **Merry-Go-Round (B):** Ball transferred into maze  
- **Ferris Wheel (C):** Ball lifted after FSR detection  
- **Piston Actuation (D):** Ball pushed onto upper slide  
- **Electromagnet ON (E):** Ball captured for elevator stage  
- **Elevator Up (F):** Stepper motor lifts ball vertically  
- **Bridge Align (G):** Servo rotates bridge to horizontal  
- **Release (H):** Electromagnet disengaged, ball drops to exit  
- **Timer → Reset (I):** 3-second delay before system reset

This structured sequencing ensured **smooth transitions**, avoided race conditions, and enabled reliable end-to-end operation.

---

## ⭐ My Key Contributions
- Designed and implemented the **FSM-based control logic**
- Integrated multiple sensors (LDR, FSR, line sensors) with actuators
- Coordinated timing, sequencing, and state transitions
- Assisted with mechanical alignment to ensure reliable sensing
- Participated in debugging timing errors and misalignments
- Contributed to documentation, testing, and final demonstration

---

## 🧪 Testing & Optimization
- Conducted repeated test runs to identify:
  - Sensor misalignment
  - Timing mismatches
  - Mechanical instability
- Fine-tuned:
  - Motor speeds
  - Sensor thresholds
  - State delays and transitions
- Achieved **consistent, repeatable ball traversal** from start to exit

---

## 🧩 Technologies & Tools
- **Controllers:** Arduino, FPGA (Quartus)
- **Programming:** Arduino IDE, FSM logic
- **Sensors:** LDR, FSR, line sensors
- **Actuators:** Stepper motors, servo motors, electromagnet, piston
- **Design:** CAD modeling, mechanical prototyping
- **Collaboration:** Team coordination, versioned documentation

---

## 🤝 Team Collaboration & Project Management
- Set up shared communication channels for coordination
- Participated in early concept development and CAD refinement
- Assisted with component sourcing and lab-based assembly
- Contributed to testing, documentation, and final presentation video

---

## 🚀 Key Learnings
- FSM-based control greatly improves reliability in multi-stage mechatronic systems
- Tight coupling between mechanical design and sensing is critical
- Small timing and alignment errors can propagate through complex systems
- Clear state definitions simplify debugging and integration

This project demonstrates **system-level thinking**, combining mechanical design, electronics, embedded software, and structured control logic.

