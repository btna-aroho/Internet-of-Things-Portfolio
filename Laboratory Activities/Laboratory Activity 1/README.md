# Laboratory Activity 1: Working with Digital Signals
## Overview
</br>
This activity demonstrates how to program an Arduino microcontroller to control multiple lights automatically. Instead of writing separate instructions for every single light, this project uses smart programming shortcuts (called Arrays and Loops) to handle a sequence of 5 LEDs efficiently.

## Code Structure
- **Variable** **Declaration:** Declares an integer array (ledPins) holding values {12, 11, 10, 9, 8} to index the digital pins programmatically.
- **Setup** **Function:** Initializes Serial communication for debugging and uses a for loop to configure every pin in the array as an OUTPUT using pinMode.
- **Loop** **Logic:** Executes two sequential loops. The first turns pins HIGH (on) with a 1000ms delay, and the second turns them LOW (off) with the same delay.

## Hardware Setup
- **Microcontroller:** Arduino Uno (R3)
- **Actuators:** 5x LED Pins (Red, Blue, Yellow, Green, Orange)
- **Components:** Breadboard, Jumper Wires, 5x Resistors
  
## Project Flow
- **Activation** **Sequence:** The code iterates through the array, turning on the LED at Pin 12, waiting 1 second, then turning on Pin 11, and so on until Pin 8.
- **Deactivation** **Sequence:** mmediately after the last LED lights up, the system restarts the list, turning off the LED at Pin 12, waiting 1 second, and continuing down to Pin 8.
- **Repetition:** The entire On/Off cycle repeats indefinitely within the main loop() function. 

## Reference
- [PDF File with compiled website links](https://github.com/btna-aroho/Internet-of-Things-Portfolio/blob/3b3529bab9e95ea7e3423e1aace3bfce6ad10889/Laboratory%20Activities/Laboratory%20Activity%201/Act1-References.pdf)

## Contributors
**Leader:** Mendez, Rachelle Yazmhine C.
### Members
- Arrojo, Betina B. (98)
- Mariano, Jamil S. (99)
