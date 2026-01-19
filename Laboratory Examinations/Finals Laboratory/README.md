# Finals Laboratory Examination
## Overview
This project establishes a physical interface for a web-based IoT system. It allows a user to press a physical button connected to an Arduino to trigger a remote action (specifically, toggling an LED) on a web server. 
The system acts as a "Serial-to-HTTP Bridge." The Arduino handles the physical hardware interactions, while a Python script running on a computer acts as a gateway, reading signals from the Arduino via USB and forwarding them as API requests to a remote server over the local network.

## Code Structure
1. **Arduino Firmware ([arduino_sender.ino](https://github.com/btna-aroho/Internet-of-Things-Portfolio/blob/main/Laboratory%20Examinations/Finals%20Laboratory/arduino_sender.ino.ino))**
   - **Initialization:** Sets up the Serial communication at 9600 baud and configures Pin 2 as an input
     with an internal pull-up resistor.
   - **Debouncing Logic:** The code implements software debouncing. It monitors the button state and
     only registers a press if the signal remains stable for more than 50 milliseconds. his prevents
     accidental double-triggering caused by the physical "bouncing" of mechanical switch contacts.
   - **State Detection:** It specifically looks for a Falling Edge (transition from HIGH to LOW).
     This ensures the signal is sent only once when the button is first pressed, not continuously while
     held down.
   - **Data Transmission:** When a valid press is detected, it sends the specific string "2" (the group number)
     over the serial connection to the computer.
3. **Python Client ([iot_client.py](https://github.com/btna-aroho/Internet-of-Things-Portfolio/blob/main/Laboratory%20Examinations/Finals%20Laboratory/iot_client.py))**
   - **Configuration:** Defines the target Serial Port (COM7), the Baud Rate, and the given API Server (http://172.20.10.3:8000)
     This enters an infinite loop (while True) monitoring the USB port for incoming data from the Arduino.
   - **API Logic**
     - It receives the group number (e.g., "2") from the Arduino.
     - It dynamically constructs a URL: http://172.20.10.3:8000/led/group/2/toggle.
     - It uses the requests library to send an HTTP GET request to that URL.
   - **Error Handling:** It includes try-except blocks to handle connection errors or serial disconnects
     
## Hardware Setup
- **Microcontroller:** Arduino Uno (R4)
- **Input Device:** Push Button
- **Connections:** USB Cable; *Internal Pull-Up Resistors is enabled in this project*
- **Breadboard and Jumper Wires**

## Project Flow
1. **User Action:** The user presses the physical button connected to the Arduino.
2. **Signal Processing (Arduino):** This is where the Arduino detects the voltage drop on Pin 2
   (HIGH to LOW). It waits 50ms to ensure the press is real and then sends the text string "2"
   via the USB cable.
3. **Data Capture (Python):** This script listening on COM7, reads the string "2". It prints
   [-] Signal received. Group Number: 2 to the console.
4. **API Request (Python):** The script targets the endpoint: http://172.20.10.3:8000/led/group/2/toggle.
   It now sends the request over the WiFi/LAN network to the server.
5. **Server Action (External):** The server at that IP address receives the command and toggles the LED associated with Group 2.
6. **Feedback:** The server sends a status code back to the Python script. It now prints to confirm
   the action was completed.

## Reference
- Generative AI has been used in support for this project.
  - [Prompts used to transact with your selected Generative AI (Gemini 3 Pro)](https://docs.google.com/document/d/1Ph4f8GnvtJRS32F7EDq53SKSUNrVf3dXvfsSIAUVcg0/edit?tab=t.0)
  - [Transaction ID or the link of the conversation](https://gemini.google.com/share/cd19b5a6c23a)

## Contributors
**Leader:** Magma, John Harold R.
### Members:
- Ambong, Jemuel Chris N.
- Arrojo, Betina B.
- Dellosa, Keren G.
- Mariano, Jamil S.
- Mendez, Rachelle Yazmhine C.
- Pascual, Audric P.
