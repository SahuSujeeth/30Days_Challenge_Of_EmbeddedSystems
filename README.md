# Embedded-Systems-30Days-Challenge
🚀 30 Days of Embedded Systems with Arduino — A daily learning challenge to build consistency, deepen embedded knowledge, and create hands-on Arduino &amp; IoT projects. Daily progress, code, and circuits documented here.

----

# 🚀 Day 0 — The Beginning of My 30 Days Embedded Systems with Arduino Challenge

Today marks the start of my 30-day journey into the world of **Embedded Systems and Arduino**.  
The goal is simple — learn something new every day, stay consistent, and document every bit of progress here.

---

## 💡 What I’m Doing
For the next 30 days, I’ll be learning, practicing, and building small embedded projects using Arduino.  
Each day, I’ll upload my code, circuit images, and short notes about what I learned.  
All my daily progress will live in this GitHub repository.

I’ll also share **weekly progress summaries** and small project highlights on LinkedIn.

---

## 🧠 My Focus
This challenge is not just about completing 30 days — it’s about improving consistency, clarity, and hands-on understanding of hardware and code working together.

---

## 🧩 Posting Plan
| Platform | Updates | Frequency |
|-----------|----------|------------|
| **GitHub** | Daily progress, code, circuits, output photos | Every Day |
| **LinkedIn** | Weekly reflections & project updates | Every Sunday |

---

## ⚙️ My Commitment
> I’ll learn for around **2 focused hours every day**,  
> no excuses, no skipping — just one step closer to mastery, each day.

---

## 💭 Reflection
Day 0 is all about setting the stage.  
Created this repository, finalized the structure, and planned the learning flow for the next 30 days.  
Feeling excited and ready to dive in from tomorrow — **Day 1 begins the real work.**

---

📅 *Challenge Duration:* 30 Days  
📍 *Started On:* [09-11-2025]  
🧠 *Daily Learning Repo:* You’re already in it 😄  

---

> “You don’t have to be great to start, but you have to start to be great.”



# 📘 Day 1 — Introduction to Embedded Systems

### 🧩 Overview
Today marks the start of my 30-Days of Embedded Systems with Arduino Challenge!  
On Day 1, I explored the **fundamentals of embedded systems** — how hardware and software integrate to form intelligent, real-time devices that power everything from washing machines to IoT nodes.

---

### ⚙️ Topics Covered
- What is an Embedded System & its Key Characteristics  
- Embedded System Building Blocks  
- Microcontroller vs Microprocessor  
- Digital & Analog Basics  
- Real-Time Concepts (Hard/Firm/Soft RT)  
- Interrupts, Timers, PWM, ADC — Core Arduino Foundations  
- Communication Interfaces (UART, SPI, I²C, CAN, etc.)  
- Embedded Software Stack  
- Power & Performance Management  
- Arduino Context — Understanding the UNO Architecture  
- Typical Embedded Project Dataflow  
- Common Interview Qs (Day-1 Level)

---

### 💭 Reflection
> Learned how embedded systems are the silent intelligence behind modern devices.  
> I now understand the roles of sensors, actuators, microcontrollers, and how real-time systems make everything respond on time.  
> Excited to dive into **Arduino basics** tomorrow and start building hands-on circuits ⚡.

---
......

📅 **Date:** 10 November 2025  
✅ **Status:** Completed  
🔗 **Detailed Notes:** [Notes.md](./Day01_IntroductionTo_EmbeddedSystems/Notes.md)



# 🔧 Day 2 — Memory Management + Arduino Basics (Button–LED with Tinkercad)

---

## 🧩 Overview

On Day 2 of my **30 Days Embedded Systems with Arduino** challenge, I focused on both:

- **Memory Management in Embedded Systems** (Flash, SRAM, EEPROM, segments)
- **Arduino Basics** (digital I/O, pin modes, simple input/output circuit)

I then built and tested a **Button-controlled LED circuit** using **two resistors**, both in **Tinkercad simulation** and on real hardware.

---

## 📚 Topics Covered

- Memory Types in Microcontrollers:
  - Flash (program storage)
  - SRAM (runtime variables, stack)
  - EEPROM (persistent small data)
- Memory Segments:
  - Code/Text, .data, .bss, stack, heap
- Arduino UNO Memory Overview:
  - 32 KB Flash, 2 KB SRAM, 1 KB EEPROM
- Arduino Sketch Basics:
  - `setup()` and `loop()`
- Digital Input & Output:
  - `pinMode()`, `digitalRead()`, `digitalWrite()`
- Button with Pull-Down Resistor
- LED with Current-Limiting Resistor
- Using **Tinkercad** for circuit simulation

---

## 🔌 Circuit Summary

### 🔹 LED:
- Anode (long leg) → **Arduino Pin 12**  
- Cathode (short leg) → **220Ω resistor → GND**

### 🔹 Button (with 10kΩ Pull-Down):
- One side of button → **5V**  
- Other side → **Arduino Pin 2**  
- Same row as pin 2 → **10kΩ resistor → GND**

### 🧠 Behavior

| Button | Pin 2 Reads | LED |
|--------|-------------|-----|
| Not Pressed | LOW | OFF |
| Pressed | HIGH | ON |

---

## 🧪 Tinkercad Simulation

I used **Tinkercad** to:

- Build the same circuit virtually  
- Test button + LED behavior  
- Verify the code before/alongside hardware

Link for the simulation to see output saved in:
👉 [tinkercad_link.txt](./Day02_MemoryMangement_ArduinoBasic/Code/tinkercad_link.txt)


---

📄 **Detailed Notes:**  
👉 [Notes.md](./Day02_MemoryMangement_ArduinoBasic/Notes.md)

📅 **Date:** 11 November 2025  
✅ **Status:** Completed

---

# 🔦 Day 3 — Multiple LEDs & Pattern Logic

Today I worked with **multiple LEDs** and learned how to create light animation patterns using Arduino.  
This step builds logical thinking needed for future topics like sequencing, motor control, buzzer tones, and real output systems.

---

### 🔧 What I Learned

- How to control multiple outputs using Arduino pins
- Use of **loops and arrays** to clean repeated LED code
- Creating patterns like:
  - Simultaneous blink (basic)
  - Sequential blink
  - Ping-Pong / Knight Rider effect
- Structured code approach (no repetition, scalable logic)

---

### 🧪 Circuit Overview

| LED | Arduino Pin | Resistor |
|-----|-------------|-----------|
| LED1 | D9 | 220Ω |
| LED2 | D8 | 220Ω |
| LED3 | D7 | 220Ω |

All cathodes are connected to **GND through resistors**.

📌 LED Rule:  
**Anode (long leg) → Arduino pin**  
**Cathode (short leg) → resistor → GND**

---

### 🧠 Behavior Examples

| Pattern Name | Description |
|--------------|------------|
| Blink All | All LEDs turn ON → wait → OFF → repeat |
| Sequential | LED1 → LED2 → LED3 → repeat |
| Ping-Pong | 1 → 2 → 3 → 2 → 1 → repeat |

---

### 📄 Code Files

| File | Function |
|------|----------|
| `pattern_basic.ino` | Turns all LEDs ON/OFF together |
| `pattern_pingpong.ino` | Knight Rider / Ping-Pong animation |

---

📷 Circuit Image will be inside the **images/** folder.

📄 Detailed notes: → [Notes.md](./Day03_Led_Patterns/Notes.md)

💻 Simulation link (optional): → `simulations/tinkercad_link.txt`
👉 [tinkercad_link.txt](./Day03_Led_Patterns/Code/tinkercad_link.txt)

---

📅 Date: **12 November 2025**  
⏳ Progress: **3 / 30 Days Complete**  

---
# 🔔 Day 04 — Buzzer Interfacing with Push Button & Slide Switch

Today’s focus was understanding how to generate sound using a **buzzer** and control it using different types of switches.  
This helped connect **input (switch)** with **output (sound)** — forming real embedded interaction.

---

## 🎯 What I Learned

✔ How buzzers work (active vs passive)  
✔ How to control sound using Arduino  
✔ How to use a **push button** as an input device  
✔ How to use a **slide switch** for stable ON/OFF control  
✔ How to apply **conditional logic (if/else)** based on switch states  
✔ How tone frequency affects how sound is perceived  

---

## 🎧 Buzzer Types

| Type | Requires tone()? | Sound Type | Use Case |
|------|------------------|------------|----------|
| **Active Buzzer** | ❌ No | Fixed beep | Alerts / alarms |
| **Passive Buzzer** | ✔ Yes | Programmable tone | Music, variable sounds |

I used a **passive buzzer**, which allowed sound frequency changes using:


---

📄 Detailed Notes: → [Notes.md](./Day04_Interfacing_Buzzer&Switch/Notes.md)

🔧 Arduino Code Files: → `/code/`

💻 Simulation Link (optional): → `simulations/tinkercad_link.txt`  
👉 [tinkercad_link.txt](./Day04_Interfacing_Buzzer&Switch/Code/tinkercad_link.txt)

🖼 Circuit Image: → `images/circuit.png`
👉 [View Circuit](./Day04_Interfacing_Buzzer&Switch/Images/)

---

📅 Date: **13 November 2025**  
⏳ Progress: **4 / 30 Days Complete**  


# 📟 Day 05 — Communication Interfaces, LCD Display & Keypad Input

Today’s learning focused on how Arduino communicates with other devices and how external input/output interfaces help build user-interactive embedded systems.

---

## 🎯 Topics Covered

- UART Serial Communication
- LCD Interfacing (I2C 16x2 Display)
- 4x4 Matrix Keypad Input System
- Understanding Data Flow Between User, Display, and Controller

---

## 🔌 Serial Communication (UART)

Serial communication allows Arduino to communicate with a computer or another device using TX/RX lines. Today, I worked with Serial Monitor to send and receive messages, observe data transfer, and practice basic debugging.

---

## 🖥️ LCD Display (16x2 with I2C)

A 16x2 LCD was connected using the I2C communication protocol, reducing wiring complexity to just two pins (SDA & SCL). Functions like cursor movement, clearing display, and multi-line formatting were explored.

---

## ⌨️ 4×4 Matrix Keypad

A keypad was interfaced to allow numeric and character input. Learned how matrix scanning works internally using rows and columns, and how keypad input can be used for passwords, menus, and system control.

---

## 🔍 Real-World Applications

- Password-based locks
- Menu navigation interfaces
- Status message displays
- Debugging and serial data logging
- User-controlled embedded systems

---

## 🧠 Key Takeaways

- UART enables communication between devices.
- I2C protocol simplifies hardware connections.
- Input (Keypad) + Output (LCD) + Controller (Arduino) = Complete Embedded Interaction System.
- These peripherals form the basis of future systems such as security locks, dashboards, industrial panels, vending machines, and IoT user interfaces.

---

📄 Detailed Notes → **[Notes.md](./Day05_SerialCommunications/Notes.md)**  
💻 Simulations → `simulations/tinkercad_links.txt`  
👉 [tinkercad_link.txt](./Day05_SerialCommunications/Code/tinkercad_link.txt)
🖼 Circuit Images → [images](./Day05_SerialCommunications/Images/)

---

📅 Progress: **Day 05 Completed**

# ⚙️ Day 06 — ADC, PWM & Motor Interfacing

Today’s learning focused on understanding how Arduino handles **analog signals**, how motor control works, and how precise output control is achieved using **PWM and servo mechanisms.**

---

## 🎯 Topics Covered

- Analog-to-Digital Conversion (ADC)
- PWM (Pulse Width Modulation)
- DC Motor Interfacing
- Servo Motor Control
- Using Analog Input (Potentiometer) to control output

---

## 1️⃣ ADC in Arduino

ADC converts an **analog voltage (0–5V)** into a **digital value (0–1023)** so the Arduino can understand real-world sensor signals.

Examples of where ADC is used:
- Potentiometers
- Temperature sensors
- Light sensors (LDR)
- Pressure sensors

Key learning:
- Analog signals are continuous.
- Digital value depends on resolution (10-bit ADC in Arduino UNO).
- Mapping analog values to meaningful output (speed, brightness, tone, angle).

---

## 2️⃣ PWM (Pulse Width Modulation)

PWM is used to simulate analog output using digital pins by varying the ON/OFF time (duty cycle).

Applications:
- LED brightness control
- Motor speed control
- Buzzer tone variation
- Servo internal control signal

Concepts learned:
- Duty cycle (%) determines output intensity
- Arduino PWM resolution: **0–255**
- Only PWM-supported pins (~ symbol) can be used

---

## 3️⃣ DC Motor Interfacing

A DC motor cannot be connected directly to Arduino due to current requirements, so a motor driver (L293D or transistor/MOSFET) is required.

Key learning points:
- Controlling DC motor direction (CW/CCW)
- Controlling speed using PWM
- External power supply importance for motors

Real-world examples:
- Fans
- Wheels in robotics
- Conveyor systems

---

## 4️⃣ Servo Motor Control

Servo motors allow precise angular movement (0–180 degrees).  
Unlike DC motors, servos work based on **position control**, not continuous rotation.

Learned:
- Signal timing defines angle
- Controlled using `servo.write(angle)` (conceptually)
- Ideal for robotics joints, RC vehicles, robotic arms, and controlled movement systems

---

## 🔍 Practical Skills Gained

✔ Reading analog values and understanding their meaning  
✔ Mapping analog input to control hardware  
✔ Adjusting motor speed using PWM  
✔ Controlling servo angles smoothly  
✔ Understanding power management and safety while working with motors  

---

## 🧠 Real-World Applications

- Volume or speed control using a dial (potentiometer)
- DIY fan speed controller
- Motor-based automation projects
- Servo-based mechanisms like robotic arms or servo-controlled locks
- Smart control systems using sensor feedback

---

## 🛠 Files Included

| File Type | Purpose |
|-----------|---------|
| Notes.md | Detailed technical explanation |
| /images | Circuit diagrams |
| /code | Examples for ADC, PWM, DC motor, and servos |
| simulations/ | Tinkercad links (optional) |

📄 Detailed Notes → `[Notes.md](./Day06_MotorControl_PWM/Notes.md)`  
💻 Simulation Links → `simulations/tinkercad_links.txt`  
👉 [tinkercad_link.txt](./Day06_MotorControl_PWM/Code/tinkercad_link.txt)
🖼 Wiring Diagrams → `/images/`[iamges](./Day06_MotorControl_PWM/Images/)

---

## 📅 Status

➡ **Day 06 Completed**  
🔜 Next: Day 07 — Week-1 Reflection & LinkedIn Update


# 🧠 Day 08 — Interrupts & Practical Applications

Today’s learning focused on understanding how **hardware interrupts** work in embedded systems and how they help microcontrollers respond instantly to real-time events. Instead of continuously checking a pin state using polling, interrupts allow the system to **pause the main program**, execute a short task, and then continue from where it stopped — improving efficiency and responsiveness.

---

## 🚦 What I Learned Today

### 🔹 1. Polling vs Interrupts
- **Polling** continuously checks the input state in the loop (slow and inefficient).
- **Interrupts** react instantly when a trigger event occurs (button press, sensor output, communication event, etc.).

### 🔹 2. Types of Interrupt Signals (Arduino)
- **LOW**
- **CHANGE**
- **RISING**
- **FALLING**

Example usage:

```cpp
attachInterrupt(digitalPinToInterrupt(2), handlerFunction, RISING);

📄 Detailed Notes → `[Notes.md](./Day08_Interrupts%20_appilcations/Notes.md)`  
💻 Simulation Links → `simulations/tinkercad_links.txt`  
👉 [tinkercad_link.txt](./Day08_Interrupts%20_appilcations/Code/tinkercad.txt)
🖼 Wiring Diagrams → `/images/`[iamges](./Day08_Interrupts%20_appilcations/Images/)


---

# 🌡️ Day 09 — Sensor Interfacing: Analog Sensors with Arduino

Today’s session focused on working with **analog sensors** that vary resistance or voltage based on environmental conditions. I interfaced three commonly used real-world sensors — **TMP36 temperature sensor, LDR (Light sensor), and Force/Pressure sensor** — and observed how their analog readings can control actuators like LEDs and buzzers.

---

## 📘 What I Learned Today

✔ How analog sensors generate varying voltage  
✔ Using `analogRead()` to capture real-time sensor values  
✔ Mapping sensor readings to meaningful outputs (temperature, light level, force)  
✔ Sensor-based event automation using LEDs and buzzers  

---

## 🔥 Project 1 — TMP36 Temperature Sensor with 3 LEDs

### 🛠 Required Components
- Arduino UNO  
- Breadboard  
- TMP36 Temperature Sensor  
- LEDs ×3  
- Resistors  
- Jumper wires  

### 🔌 Circuit Overview

| TMP36 Pin | Connection |
|-----------|------------|
| Pin 1 — V_in | → 5V |
| Pin 2 — V_out | → A0 |
| Pin 3 — GND | → GND |

#### LED Connections:

- Digital Pins **2, 3, and 4 → LED anodes**
- LED cathodes → resistor → GND

Used LEDs as **temperature indicators** (Ex: LOW/MED/HIGH temp).

---

## 🔦 Project 2 — LDR (Light Sensor) with LED Control

### 🛠 Required Components
- Arduino UNO  
- LDR (Photoresistor)  
- 10kΩ resistor  
- LED + resistor  
- Breadboard  

### 🔌 Circuit Overview

| Component | Connection |
|----------|------------|
| LDR Terminal 1 | → 5V |
| LDR Terminal 2 | → A0 + 10kΩ resistor to GND |
| LED Anode | → Digital Pin 9 |
| LED Cathode | → 220Ω resistor → GND |

Here, the LED turns ON/OFF based on brightness — used as a basic **automatic night lamp system**.

---

## 🏋️ Project 3 — Force/Pressure Sensor with Buzzer

### 🛠 Required Components
- Arduino UNO  
- Pressure/Force Sensor  
- Buzzer  
- 10kΩ resistor  
- Breadboard  

### 🔌 Circuit Overview

| Component | Connection |
|-----------|------------|
| Force Sensor Terminal 1 | → 5V |
| Force Sensor Terminal 2 | → A0 + 10kΩ resistor to GND |
| Buzzer Positive Pin | → Digital Pin 3 |
| Buzzer Negative Pin | → GND |

Buzzer activates when pressure crosses a threshold (e.g., touch detection, weight sensing).


📄 Detailed Notes → `[Notes.md](./Day09_AnalogSensors/Notes.md)`  
💻 Simulation Links → `simulations/tinkercad_links.txt`  
👉 [tinkercad_link.txt](./Day09_AnalogSensors/Code/tinkercad.txt)
🖼 Wiring Diagrams → `/images/`[iamges](./Day09_AnalogSensors/Images/)

---

# 🔍 Day 12 — Digital Sensors Interfacing with Arduino

Today’s focus was on interfacing commonly used **digital sensors** with Arduino and understanding how external environmental conditions trigger system responses. These sensors detect motion, gas levels, distance, or infrared signals and play a key role in automation and IoT-based applications.

---

## 📘 Topics Covered

- PIR Motion Sensor Interfacing
- Gas Sensor (MQ Series) Interfacing
- Ultrasonic Distance Sensor (HC-SR04)
- IR Sensor Interfacing (with basic LED output)

Each sensor demonstrates how digital input signals can control actuators such as LEDs and buzzers based on real-time environmental changes.

---

---

## 1️⃣ PIR Motion Sensor Interfacing

The PIR (Passive Infrared) sensor detects motion based on body heat and outputs a digital HIGH signal when movement is detected.

### 🛠 Required Components
- Arduino UNO  
- PIR Sensor  
- LED  
- Resistor  
- Breadboard  

### 🔌 Connections

| PIR Pin | Connection |
|---------|-----------|
| VCC | → 5V |
| GND | → GND |
| OUT | → Digital Pin 2 |

| LED | Connection |
|-----|-----------|
| Anode | → Digital Pin 13 (via resistor) |
| Cathode | → GND |

📌 **Application Example:** Basic motion detection system (security alarm / automatic lighting).

---

---

## 2️⃣ Gas Sensor (MQ-2) Interfacing

Gas sensors detect smoke, LPG, methane, and combustible gases. The output is analog or digital depending on the module.

### 🛠 Required Components
- Arduino UNO  
- Gas Sensor (MQ-2 example)  
- LED  
- Buzzer  
- Resistor  
- Breadboard  

### 🔌 Connections

| Component | Connection |
|-----------|------------|
| MQ-2 VCC | → 5V |
| MQ-2 GND | → GND |
| MQ-2 Output (A0) | → A0 |

| LED | → Pin 13 → GND (via resistor)
| Buzzer | → Pin 3 → GND |

📌 **Application Example:** Fire alarm, gas leak detector.

---

---

## 3️⃣ Ultrasonic Sensor Interfacing (HC-SR04)

This sensor measures distance by transmitting and receiving high-frequency sound pulses.

### 🛠 Required Components
- Arduino UNO  
- HC-SR04 Sensor  
- Connecting Wires  

### 🔌 Pin Roles

| Pin | Description |
|-----|-------------|
| VCC | Power supply (5V) |
| GND | Ground |
| Trig | Sends ultrasonic pulse |
| Echo | Receives reflected pulse |

### 🔌 Connections

| Pin | Arduino Pin |
|------|------------|
| VCC | 5V |
| GND | GND |
| Trig | 10 |
| Echo | 9 |

📌 **Application Example:** Distance monitoring, parking assist system, obstacle detection for robots.

---

---

## 4️⃣ IR Sensor Interfacing with Arduino

IR sensors detect reflected infrared light and are often used for obstacle detection or remote control decoding.

### 🛠 Required Components
- Arduino UNO  
- IR Sensor  
- LED  
- 220Ω Resistor  
- IR Remote (optional)  
- Breadboard  

### 🔌 Connections

| IR Pin | Arduino |
|--------|---------|
| VCC | 5V |
| GND | GND |
| OUT | Pin 3 |

| LED | → Pin 7 → Resistor → GND |

📌 **Application Example:** Line followers, IR remote systems, object detection.

---

---

## ✨ Reflection

Today was a key step toward building **automation and smart detection systems**. Each sensor provided a real-world scenario where Arduino reacts to motion, gas levels, distance, or IR signals — forming the basis of home automation, robotics, and IoT applications.

---

🗓️ **Status:** ✔ Completed  
📄 Notes: `Notes.md`  
🧪 Simulation: `tinkercad_links.txt`.

---
# 🔍 Day 13 — Revised all the sensors once again...










