# 📘 Day 05 — Communication Interfaces, LCD & 4×4 Keypad

---

## 1️⃣ UART — Serial Communication (Asynchronous)

### What it is  
UART (Universal Asynchronous Receiver–Transmitter) is a **serial communication protocol** used for data exchange between Arduino and other devices (like a PC, Bluetooth module, GPS, etc.).

### Key Characteristics

- Uses **two main lines**:
  - TX → Transmit data
  - RX → Receive data
- **Asynchronous** → No separate clock line; both sides agree on a baud rate.
- Data is sent **bit by bit** in frames (start bit, data bits, optional parity, stop bit).
- Common baud rates: 9600, 19200, 38400, 57600, 115200 bits per second.

### Use Cases

- Sending debug messages to Serial Monitor
- Communicating with Bluetooth modules
- GPS modules, GSM modules, serial sensors

---

## 2️⃣ SPI — Serial Peripheral Interface (Synchronous, High-Speed)

### What it is  
SPI is a **synchronous, full-duplex, high-speed** communication protocol used mainly for fast data transfer between a master (usually microcontroller) and one or more slave devices.

### Lines Used

- SCK → Serial Clock (from Master)
- MOSI → Master Out, Slave In
- MISO → Master In, Slave Out
- SS (or CS) → Slave Select / Chip Select (one per slave)

### Key Characteristics

- **Full-duplex**: Data can be sent and received at the same time.
- Very **high speed** compared to UART and I²C.
- Typically used on the same PCB (short distance).

### Use Cases

- SD cards
- High-speed sensors
- TFT/OLED displays
- External ADC/DACs
- Flash memory chips

### Pros & Cons

- Pros:
  - Very fast
  - Simple hardware concept
- Cons:
  - Requires more wires
  - One chip-select line per slave device

---

## 3️⃣ I²C — Inter-Integrated Circuit (Two-Wire Bus)

### What it is  
I²C is a **two-wire, synchronous, multi-master, multi-slave** communication protocol, ideal for connecting multiple low-speed peripherals using only two lines.

### Lines Used

- SDA → Serial Data
- SCL → Serial Clock

### Key Characteristics

- Each device has a unique **address** on the bus.
- Multiple devices share the same two wires.
- Requires **pull-up resistors** on SDA and SCL.
- Common speeds: 100 kHz (Standard), 400 kHz (Fast), 1 MHz (Fast+).

### Use Cases

- Sensors (temperature, pressure, IMU, RTC)
- EEPROMs
- I²C LCDs
- IO expanders

### Pros & Cons

- Pros:
  - Only 2 wires for many devices
  - Address-based communication
- Cons:
  - Slower than SPI
  - More complex protocol than UART

---

## 4️⃣ 16×2 LCD Interfacing (I²C Based)

### Purpose  
A 16×2 LCD is used to display text, messages, menu items, and sensor values, making embedded systems **more user-friendly** without needing a computer screen.

### Key Points

- 16 columns × 2 rows → 32 characters total.
- Internally controlled by an HD44780-compatible controller.
- When used with an **I²C backpack module**, only **SDA and SCL** pins are needed from Arduino.
- Common I²C addresses: 0x27 or 0x3F (configurable).

### Features Explored

- Initializing the LCD and turning on the backlight.
- Writing text on first and second lines.
- Moving cursor to specific positions.
- Clearing display and updating values.

### Why I²C LCD is Preferred

| Feature           | Parallel LCD        | I²C LCD             |
|------------------|---------------------|---------------------|
| Required Pins    | 6–8                 | 2 (SDA, SCL)        |
| Wiring           | Complex             | Simple & clean      |
| Scalability      | Low (too many pins) | High (frees pins)   |

---

## 5️⃣ 4×4 Matrix Keypad

### What it is  
A 4×4 keypad is a **matrix of 16 keys** arranged in 4 rows and 4 columns. It allows user input like numbers, symbols, and control keys.

### Physical Layout

Example layout:

1 2 3 A
4 5 6 B
7 8 9 C
. 0 # D


### Electrical Concept

- 4 Row lines (R1–R4)
- 4 Column lines (C1–C4)
- Each key press connects one row line to one column line.

### Working Principle (Scanning)

1. Microcontroller sets one row HIGH at a time.
2. Reads all columns to check if any column is active.
3. By combining row index + column index → identifies which key was pressed.
4. Repeats scanning quickly so it feels real-time.

### Use Cases

- PIN/password input
- Menu selection
- Calculator input
- Mode selection in embedded systems

---

## 6️⃣ System Integration — Putting It All Together

Conceptual flow combining today’s topics:

```text
User Input (4×4 Keypad)
          ↓
    Microcontroller (Arduino)
     ├─ Communicates with PC via UART Serial (for debugging/logging)
     ├─ Communicates with LCD via I²C (for display)
     └─ Can communicate with sensors/memory via SPI / I²C
          ↓
Visual Feedback (16×2 LCD + Serial Monitor)
