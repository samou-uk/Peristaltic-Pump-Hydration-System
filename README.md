# Peristaltic Pump Hydration System
*(Peristaltic Pump, Embedded Control)*

A microcontroller-based hydration delivery system designed for long-duration sim-racing sessions.  
The goal is to reduce fatigue and distraction during 4–8 hour endurance races by enabling **hands-free, push-to-dispense hydration** with real-time monitoring and fault detection.

Yes, it also tells you:  
> *“Kimi, you will have the drink.”*

That part is intentional.

---

## Motivation

During long endurance simulation sessions, hydration becomes a limiting factor:
- Manual drinking breaks disrupt focus
- Fatigue increases reaction time
- Forgetting to hydrate leads to poor late-stint performance

This project explores how a small embedded control system can solve a very human problem by combining:
- simple hardware
- clear feedback
- conservative, failure-aware logic

---

## System Overview

The system consists of four main layers:

### 1. Human Interface
- Momentary **push-and-hold button** for dispensing
- **16x2 LCD** providing real-time status and feedback

### 2. Control Logic
- **Arduino Nano**
- State-based logic for idle, dispensing, and fault conditions
- Lockouts to prevent accidental continuous dispensing

### 3. Actuation
- **12V food-grade peristaltic pump**
- Motor driven via an **H-bridge** for safe current handling
- Separate logic (5V) and motor (12V) power domains

### 4. Sensing & Safety
- Inline **flow sensor** to measure real-time flow rate
- Flow-based detection of empty or obstructed conditions
- Automatic pump shutdown on fault

---

## Key Features

- **Push-to-dispense control**  
  Pump runs only while the button is held.

- **Real-time flow monitoring**  
  Displays live flow rate during dispensing.

- **Fault detection (empty / no-flow)**  
  If the pump runs without detected flow, the system shuts down and alerts the user.

- **User feedback via LCD**  
  Clear system states, including contextual messages such as:
  > *“Kimi, you will have the drink.”*  
  > *“Kimi, you will not have the drink.”*

- **Electrical isolation & protection**  
  - Separate power rails (12V motor, 5V logic)
  - Shared ground reference
  - Motor protection handled by driver circuitry
  - Conservative current handling

---

## Hardware Components

- Arduino Nano
- 12V food-grade peristaltic pump
- H-bridge motor driver
- Inline flow sensor
- Food-grade tubing and check valve
- Hydration bladder
- 16x2 I2C LCD
- Momentary pushbutton
- 3D-printed enclosure (custom CAD)

---

## Design Principles

This project intentionally prioritizes:
- **Reliability over complexity**
- **Clear failure modes**
- **Minimal user interaction**
- **Separation of concerns** (logic vs power vs fluid)

While built for sim-racing, the design principles mirror those used in production automation and control systems:
- feedback-driven decisions
- fault detection
- human-in-the-loop interfaces
- conservative safety assumptions

---

## Known Limitations

- Not designed for medical or professional motorsport use
- Flow calibration depends on sensor accuracy and tubing consistency
- Assumes single-direction pumping (no back-flush)

---

## Why This Exists

Partially for endurance racing.  
Partially for learning.  
Partially for the meme.

Mostly as an exercise in:
- systems thinking
- control logic
- and building something small that actually works.

---

## License

MIT (because this should never be proprietary).

---

## Final Note

Hydration is important.  
Feedback is important.  
And sometimes, a system telling you  
**“Kimi, you will have the drink”**  
is exactly the motivation you need mid-stint.

