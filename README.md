# IR Sensor-Based Object Counter

## Overview
This project is a **sensor-based object counter** built on **zero PCB** using:
- **IR LED + Photodiode** for object detection
- **LM358 Comparator** for signal conditioning
- **NE555 Monostable** for debouncing and pulse shaping
- **CD4033 Decade Counter ICs** for driving 7-segment displays

It counts objects passing through the IR beam and displays the total on a 2-digit common cathode 7-segment display.

---

## Features
- Reliable counting with **debouncing via NE555**
- Modular design for easy debugging (test points available)
- Works in **low-light and indoor** environments
- Reset button to clear the count
- Powered from 6V supply with onboard 7806 regulator

---

## Components Used

| Component        | Quantity | Notes                          |
|------------------|----------|--------------------------------|
| SFH482 IR LED    | 1        | Transmitter                    |
| SFH206 Photodiode| 1        | Receiver                       |
| LM358N           | 1        | Dual Op-Amp (used as comparator)|
| NE555 Timer      | 1        | Monostable for pulse shaping   |
| CD4033N          | 2        | 7-segment driver & counter     |
| HD-H101 Display  | 2        | Common cathode                 |
| 7806 Regulator   | 1        | Power regulation               |
| Resistors, Caps  | -        | Passive components             |
| Push Button      | 1        | Reset                          |

---

## Circuit Diagram
```plaintext
schematic.pdf
```

---

## Working Principle
1. **Object detection** – IR LED emits a beam to the photodiode. When an object blocks the beam, the photodiode voltage changes.
2. **Signal conditioning** – LM358 compares the photodiode output against a reference voltage and outputs a digital signal.
3. **Debouncing** – NE555 monostable generates a fixed-width pulse for each beam break to prevent false triggering.
4. **Counting** – CD4033 increments the count on the 7-segment display.

---

## Assembly & Testing
1. Assemble the circuit as per schematic.
2. Power with 6V DC.
3. Align IR LED and photodiode for maximum sensitivity.
4. Test with objects moving through the beam — the count should increment.
5. Press reset to clear count.

---

## 📂 Repository Structure
```plaintext
/docs/       - Project documentation, datasheets, and diagrams
/hardware/   - Schematic, PCB, and wiring images
/images/     - Project build photos
/README.md   - Main project guide
