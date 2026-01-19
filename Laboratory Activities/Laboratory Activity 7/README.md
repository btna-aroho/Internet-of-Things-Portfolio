# Laboratory Activity 7: Controllling Arduino using FastAPI
## Overview
This activity demonstrates a Web-Controlled IoT System that integrates physical hardware control with a modern web API. It evolves beyond simple serial communication by using FastAPI (a Python web framework) to allow external applications (like a web browser or mobile app) to control the Arduino.
This project features the dual-control capability:
- Users can press physical buttons on the breadboard to toggle LEDs.
- Users can send HTTP web requests to toggle the LEDs from a computer.

## Code Structure
1. **Arduino Firmware ([arduino.ino](https://github.com/btna-aroho/Internet-of-Things-Portfolio/blob/main/Laboratory%20Activities/Laboratory%20Activity%207/arduino.ino))**
  - **Pin Definition:** Defines the LED and buttons to the designated pin numbers.
  - **Serial:** Continuously waits for single-character commands from the computer.
    - RED ('1'), GREEN ('2'), BLUE ('3'); Turns all LEDs ON ('o'), Turns all LEDs OFF ('f')
  - **Physical:** If Button 1 is pressed, it toggles the Red LED and sends a confirmation message back to the computer.
2. **Python API Server ([arduino.py](https://github.com/btna-aroho/Internet-of-Things-Portfolio/blob/main/Laboratory%20Activities/Laboratory%20Activity%207/arduino.py))**
    - **Setup:** Connects to the Arduino via Serial Port COM7 at 9600 baud.
    - **FastAPI Framework:** reates a local web server to listen for internet-style requests.
      - **GET /led/on:** Sends the character "o" to Arduino (All On).
      - **GET /led/off:** Sends the character "f" to Arduino (All Off).
      - **GET /led/{color}:** Accepts "red", "green", or "blue". It translates these words into the characters "1", "2", or "3" to toggle specific lights.

## Hardware Setup
- **Microcontroller:** Arduino Uno (R4)
- **Components:** 3x Push Buttons; 3x Resistors; 3x LED Pins (Red, Green, Blue)
- **Breadboard and Jumper Wires**

## Project Flow
[Video Simulating the Breadboard and its corresponding Circuit Diagram on TinkerCad](https://drive.google.com/file/d/1DQ9WWUWmo1qZMCe8QqU39jhmn8ZmGocY/view)
</br>
1. Web Control: Remote
   - **Request:** The user types http://localhost:8000/led/red into their web browser.
   - **API Processing:** The Python script receives this request at the /led/{color} endpoint.
   - **Translation:** Python identifies the color "red" and sends the character "1" via USB to the Arduino.
   - Execution: The Arduino reads "1", executes toggleLED(redPin), and the Red light turns on/off.
2. Physical Control: Manual
   - **Action:** A user presses the Middle Button (Pin 11) on the breadboard.
   - **Detection:** The Arduino detects a HIGH signal on Pin 11. This immediately toggles the Green LED (Pin 6)
   - **Feedback:** It sends the text "Button 2 Pressed: Green Toggled" back to the Python console so the administrator knows a manual action occurred.

## Reference
- Generative AI has been used in support for this project.
  - [Prompts used to transact with your selected Generative AI (Gemini 3 Pro)](https://docs.google.com/document/d/1MN57WclmEDDDeA7Bta_moRSLxrkAH41zfC28ILxsMrw/edit?tab=t.0)
  - [Transaction ID or the link of the conversation](https://gemini.google.com/share/3e477ec98a37)

## Contributors
**Leader:** Arrojo, Betina B.
### Members:
- Ambong, Jemuel Chris N.
- Dellosa, Keren G.
- Mariano, Jamil S.
- Magma, John Harold R.
- Mendez, Rachelle Yazmhine C.
- Pascual, Audric P.
