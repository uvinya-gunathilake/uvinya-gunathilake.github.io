# PLC & SCADA-Based Automation of FESTO Stations

**Industrial Automation · PLC Programming · SCADA · OOAD · Ladder Logic**  
Curtin University — Mechatronics Engineering (Group Project)

---

## Project Overview
This project involved the design and implementation of an **integrated industrial automation system** for three FESTO stations: **Distributing, Testing, and Sorting**. The system was controlled using **PLC ladder logic** and supervised through a **SCADA interface**, with a strong emphasis on **Object-Oriented Analysis and Design (OOAD)**, modular programming, and real-time monitoring.

---

## My Role & Responsibilities
I was primarily responsible for the **control logic design, system modelling, and debugging** of the FESTO stations. My work focused on translating system requirements into structured control logic and ensuring reliable interaction between sensors, actuators, PLC logic, and the SCADA interface.

### My Key Contributions
- Modelled station behavior using **Object-Oriented Analysis and finite state diagrams**
- Designed and implemented **PLC ladder logic** for multiple station processes
- Developed **modular function blocks** to enable code reuse and scalability
- Integrated sensor inputs and actuator outputs into the PLC program
- Debugged timing issues, logic conflicts, and sensor-state mismatches
- Assisted with **SCADA variable mapping** and operational testing
- Documented system behavior, logic flow, and troubleshooting procedures

---

## Object-Oriented Analysis & Design (OOAD)

OOAD was used to model each FESTO station as a collection of interacting objects with defined states and behaviors. **Finite State Diagrams** were developed to represent the lifecycle of station components, ensuring predictable state transitions and structured logic design.

### Why OOAD Was Effective
- Enabled accurate **real-world modelling** of distributing, testing, and sorting processes
- Improved **modularity**, making individual stations easier to update and maintain
- Reduced long-term maintenance effort through encapsulation and abstraction
- Supported clear communication within the team using a shared design framework

---

## Code Reuse Using Function Blocks

To improve scalability and maintainability, I implemented control logic using **function blocks**.

### What I Did
- Designed reusable function blocks for repeated station operations
- Defined clear interfaces with well-structured inputs and outputs
- Encapsulated internal logic to prevent unintended interference
- Tested function blocks independently before integration

### Outcome
- Faster development time  
- Cleaner and more readable ladder logic  
- Improved reliability due to reuse of tested logic  

---

## PLC Ladder Logic Development

### Major Achievement
One of my major contributions was improving **diagnostics and debugging efficiency** through well-structured ladder logic. The visual nature of ladder diagrams made it easier to trace data bit states and verify correct operation of sensors and actuators.

### How I Approached It
- Broke control logic into logical, sequential rungs
- Incrementally tested individual rungs and subsystems
- Verified sensor inputs and actuator outputs against intended station behavior
- Used descriptive naming conventions for clarity

This approach significantly improved system reliability and reduced troubleshooting time.

---

## Challenges & Lessons Learned (Ladder Logic)

### Identified Challenge
As station logic became more complex, ladder diagrams grew large and difficult to interpret, especially when multiple team members contributed to the same codebase.

### How I Addressed It
- Modularized ladder logic into smaller functional sections
- Added detailed comments explaining logic intent
- Participated in team reviews to align logic structure
- Maintained consistency in naming and layout

This experience highlighted the importance of **code readability and documentation** in industrial automation.

---

## SCADA System Integration

### My Involvement
- Assisted in mapping PLC variables to SCADA tags
- Helped test real-time monitoring of sensors and actuators
- Validated start, stop, reset, and fault-handling functions
- Supported system-level testing across all three stations

### Key Achievement
The SCADA interface enabled **remote monitoring and control** of the entire system through a graphical dashboard, improving operational efficiency and ease of use.

---

## SCADA Security Considerations
During development, I identified that SCADA communication protocols can be vulnerable due to weak authentication and encryption.

### Key Takeaways
- Importance of secure communication protocols
- Need for strong authentication and access control
- Value of continuous monitoring and security updates

This reinforced my awareness of **cybersecurity considerations in industrial automation**.

---

## Technologies & Tools
- **PLC Programming:** Ladder Logic  
- **Design Methodology:** OOAD, Finite State Diagrams  
- **SCADA:** Real-time monitoring and control  
- **Automation Hardware:** Sensors, actuators, motors  
- **Documentation & Testing:** Debugging, validation, reporting  

---
