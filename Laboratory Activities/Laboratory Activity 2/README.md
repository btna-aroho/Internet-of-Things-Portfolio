# Laboratory Activity 2: Working with Analog Signals
## Overview
</br>
This activity is an Arduino-based circuit designed to control a series of five LEDs sequentially. It serves as an introduction to IoT concepts, demonstrating how to use arrays and loops to manage multiple hardware outputs efficiently.

## Code Structure
- **Variable** **Declaration:** Defines an array ledpins[] containing {12, 11, 10, 9, 8} to identify the connections and defines an integer lednum set to 5 to store the total of LEDs.
- **Setup** **Function:** This uses a while loop to iterate through the pins.
- **Loop** **Logic:**
  - **Activation** **Loop:** A while loop iterates through the array, using analogWrite(ledpins[i], 255) to set the LEDs to full brightness. This includes a 1-second delay between each light.
  - **Deactivation** **Loop:** A second while loop resets the counter and iterates through the array again, using analogWrite(ledpins[i], 0) to turn the LEDs off with a 1-second delay.
## Hardware Setup
- **Microcontroller:** Arduino Uno (R3)
- **Components:** 5x LED Pins (Red, Yellow, Blue, Green, Orange), 5x resistors
- **Breadboard and Wires**
## Project Flow
- **Sequential ON:** tarting at index 0 (Pin 12), the code enters the first while loop. The first LED turns fully ON. The system waits 1 second, then moves to Pin 11, repeating until Pin 8 is lit.
- **Sequential OFF:** fter all lights are lit, the code enters the second while loop. Starting back at Pin 12, the first LED turns OFF. The system waits 1 second, then moves to Pin 11, repeating until all lights are out.
- **Loop Logic:** The main loop() function restarts, and the cycle begins again from the top.

## Reference
- [PDF File with compiled website links] (https://github.com/btna-aroho/Internet-of-Things-Portfolio/blob/main/Laboratory%20Activities/Laboratory%20Activity%202/Act2-References.pdf)

## Contributors
**Leader:** Mariano, Jamil S.
### Members:
- Arrojo, Betina B. (99)
- Mendez, Rachelle Yazmhine C. (98)
