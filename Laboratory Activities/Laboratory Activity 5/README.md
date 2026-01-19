# Laboratory Activity 5: Receiving Serial Connection using Arduino from Python
## Overview
</br>
This activity establishes a bi-directional communication system between a computer (running Python) and a microcontroller (Arduino). The system is designed to allow a user to remotely control three LEDs (Red, Green, and Blue) via a Command Line Interface (CLI).

## Code Structure
- **Main Firmware ([LabSerialAssignment.ino](https://github.com/btna-aroho/Internet-of-Things-Portfolio/blob/main/Laboratory%20Activities/Laboratory%20Activity%205/LabSerialAssignment.ino.ino)):** Initializes the Serial communication at 9600 baud and calls initLEDs() to prepare the hardware. For the loop, this continuously checks for incoming serial data. This reads characters one by one, filters out empty newline characters, and passes valid commands to processInput.
- **Hardware Logic ([led_control.h](https://github.com/btna-aroho/Internet-of-Things-Portfolio/blob/main/Laboratory%20Activities/Laboratory%20Activity%205/led_control.h))** 
  - **Definitions:** Assigns names to pins: RED_PIN (8), GREEN_PIN (9), and BLUE_PIN (10).
  - **Functions**
    - **toggleLED(int pin):** Reads the current state of a light and switches it to the opposite state.
    - **setAllLEDs(int state):** Forces all three LEDs to either HIGH or LOW simultaneously.
    - **processInput(char command):** A switch-case structure that translates letters ('R', 'G', 'B', 'A', 'O') into hardware actions.
- **Control Script ([led_controller.py](https://github.com/btna-aroho/Internet-of-Things-Portfolio/blob/main/Laboratory%20Activities/Laboratory%20Activity%205/led_controller.py)):** Uses the serial library to connect to the Arduino (configured here as port 'COM7'). This also displays a menu and waits for user input and sends the typed character to the Arduino and confirms the action on screen.

## Hardware Setup
- **Microcontroller:** Arduino Uno (R4)
- **Components:** 3x LED Pins; 3x Resistors
- **Breadboard and Jumper Wires**

## Project Flow
[Video Simulation of the Breadboard and its Corresponding Circuit Diagram on Tinkercad](https://drive.google.com/file/d/15RCLJFpSOGnHZq50F7RV-LdF9hiP91E_/view)
</br>

- **Initialization:** The Python script is started on the computer, opening a connection to the Arduino. The Arduino initializes pins 8, 9, and 10 as outputs and ensures they start OFF.
- **User Input:** The user sees a menu on their computer screen and types a letter.
- **Transmission:** The Python script encodes this letter and sends it over the USB cable to the Arduino.
- **Process:** The Arduino receives the letter R/G/B, the processInput function identifies the letter matches the LED case. This will not calls toggleLED().
- **Action:** If the desired LED was off, it turns ON. If it was on, it turns OFF.
- **Loop:** The Python menu reappears, ready for the next command.

## Reference
- **Generative AI** has been used in suuport for this project.
  - [Prompt used to transact with Generative AI (Gemini 3 Pro)](https://docs.google.com/document/d/1Fe5OqBTM9iATZMIurfX4jmZpX0Domhsl6qaz1dQoqu0/edit?tab=t.0)
  - [Transaction ID or the link of the conversation](https://gemini.google.com/share/4a584b09de8c)

## Contributors
**Leader:** Magma, John Harold R.
### Members:
- Ambong, Jemuel Chris N.
- Arrojo, Betina B.
- Dellosa, Keren G.
- Mariano, Jamil S.
- Mendez, Rachelle Yazmhine C.
- Pascual, Audric P.
