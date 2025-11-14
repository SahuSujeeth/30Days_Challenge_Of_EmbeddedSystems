# 🧠 Day 2 — Memory Management + Arduino Basics + Button–LED Circuit

---

## 1️⃣ Overview

Today I combined **theory + practice**:

- Understood how memory works in a microcontroller  
- Saw where program and variables are stored in **Flash, SRAM, EEPROM**  
- Learned basic Arduino programming structure (`setup()` + `loop()`)  
- Built a **Button + LED** circuit using **two resistors**  
- Simulated and tested everything in **Tinkercad** before/along with hardware

---

## 2️⃣ Memory Types in Embedded Systems

Embedded systems use different types of memory, each with a specific purpose:

### 🔹 Flash Memory
- **Non-volatile** → data stays even after power off  
- Stores the **program code (firmware)**  
- On Arduino UNO (ATmega328P): **32 KB Flash**

When we click **Upload** in Arduino IDE, the compiled program (.hex file) is written into Flash.

---

### 🔹 SRAM (Static RAM)
- **Volatile** → data is lost when power is off  
- Used for:
  - Local variables  
  - Global variables **while program is running**  
  - Function call stack  
  - (Optional) heap for dynamic memory  
- On Arduino UNO: **2 KB SRAM** (very small)

💡 Important:  
We must be careful with:
- Big arrays  
- Large `String` objects  
- Deep recursion  

Because they can **overflow** the limited SRAM and cause weird behavior.

---

### 🔹 EEPROM
- **Non-volatile**, like Flash  
- Meant for storing **small pieces of data permanently**  
  - Device ID, config, thresholds, calibration values  
- On Arduino UNO: **1 KB EEPROM**  

---

## 3️⃣ Memory Segments (How variables & code are stored)

In a typical embedded C/C++ program:

- **Code / Text Segment (Flash):**  
  Stores all compiled instructions (functions, logic).

- **.data Segment (SRAM):**  
  Stores **initialized global/static** variables.  
  Example:
  ```cpp
  int x = 10;
  static int count = 5;

- **.bss Segment (SRAM):**  
  Stores **uninitialized or zero-intialised global/static varialbes**.  
  Example:
  ```cpp
  int flag;
  static int index;

- **. Stack (SRAM):**  
Used for function calls and local variables.
Example:
void foo() {
  int a = 5; // on stack
}

- **. Heap (SRAM):**  
Used when using malloc / new (dynamic memory).
On small MCUs like Arduino UNO, heap use is usually avoided.

 ## 4️⃣ Arduino UNO Memory Summary
Flash: 32 KB → program.
SRAM: 2 KB → variables, stack, runtime data.
EEPROM: 1 KB → permanent small data.

## 5️⃣ Arduino Basics – Sketch Structure

Every Arduino sketch has two main functions:

void setup() {
  // runs once at startup/reset
}

void loop() {
  // runs again and again forever
}

setup() → used to initialize pin modes, Serial, etc.

loop() → main application logic, executes continuously.

## 6️⃣ Digital Input & Output – Button and LED
🔹 Pin Modes
pinMode(pin, OUTPUT);      // to drive LED, buzzer, relay...
pinMode(pin, INPUT);       // to read button/sensor with external resistor
pinMode(pin, INPUT_PULLUP);// to read button with internal pull-up


OUTPUT: Arduino pin drives HIGH (5V) or LOW (0V)

INPUT: Arduino pin reads external voltage

INPUT_PULLUP: Enables internal pull-up resistor (default HIGH, pressed = LOW)