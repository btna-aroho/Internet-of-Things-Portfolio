# Laboratory Activity 6: Bidirectional Control using Arduino and Python
## Overview
</br>
This activity establishes a bidirectional communication loop between an Arduino microcontroller and a Python script running on a computer. The system functions as a "feedback loop" where physical interactions on the Arduino (button presses) are sent to the computer for processing, and the computer sends commands back to the Arduino to control hardware outputs (LEDs).

## Code Structure
1. **Arduino Firmware ([lab_serial.ino](https://github.com/btna-aroho/Internet-of-Things-Portfolio/blob/main/Laboratory%20Activities/Laboratory%20Activity%206/lab_serial.ino))**
   - **Pin Definitions:** Defines Output LEDs on pins 5, 6, and 7, and Input Buttons on pins 10, 11, and 12.
   - **Input Handling (handleInboundSerial):** Listens for commands from the computer; meaning it reads incoming strings and trims whitespace and it checks for specific characters: '1' toggles Red, '2' toggles Green, and '3' toggles Blue.
   - **Output Handling (handleOutboundButtons):** Monitors physical button presses. It uses Debouncing Logic (millis() and debounceDelay) to ensure one button press doesn't accidentally register as multiple clicks due to mechanical noise. When a stable press is detected on Button 1, 2, or 3, it sends the character 'R', 'G', or 'B' to the computer.
2. **Python Script ([lab_serial.py](https://github.com/btna-aroho/Internet-of-Things-Portfolio/blob/main/Laboratory%20Activities/Laboratory%20Activity%206/lab_serial.py))**
   - **Connection:** Establishes a connection to the Arduino on COM4 at 9600 baud.
   - **Loop Logic:** Continuously reads data from the serial port. This means that if it receives "R" (from the Arduino), it prepares command '1'. If "G", it prepares '2'. If "B", it prepares '3'; then it immediately writes the new command number back to the Arduino to trigger the light.

## Hardware Setup
- **Microcontroller:** Arduino Uno (R4)
- **Components:** 3x Push Buttons; 3x LED Pins; 3x Resistors
- **Breadboard and Jumper Wires** 

## Project Flow
- Video Simulation of the Breadboard and its corresponding Circuit Diagram on TinkerCad
  - [Button](https://drive.google.com/file/d/10kqOOeIsctiN_6O5_a5E4hzs-qq8XbY7/view?usp=drive_link)
  - [Serial Monitor](https://drive.google.com/file/d/1utTcliTX3dfcBgLXUuTGZroUfQGzCsci/view?usp=drive_link)
1. When you press Button 1 on the breadboard, the Arduino detects the press, debounces the signal, and sends the letter "R" up the USB cable to the computer.
2. The Python script receives "R". It runs a logic check: "If input is R, send back 1". This will sends the character "1" down the USD cable to the Arduino.
3. The Arduino receives "1". It executes the command digitalWrite(RED_LED_PIN, !digitalRead(RED_LED_PIN)), which flips the Red LED on or off.

## Reference
- **Generative AI** has been used in support for this project.
  - [Transaction ID or the link of the conversation of Generative AI(Gemini 3 Pro)](https://gemini.google.com/share/2d25879716f8)

## Contributors
**Leader:** Mendez, Rachelle Yazmhine C. 
### Members:
- Ambong, Jemuel Chris N.
- Arrojo, Betina B.
- Dellosa, Keren G.
- Mariano, Jamil S.
- Magma, John Harold R.
- Pascual, Audric P.
