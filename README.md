# Laboratory Portfolio in Internet of Things (COSC 111B - CS Elective 3) 
This repository contains a list of submitted laboratory activities and laboratory exams in the fulfillment of the requirements for the Internet of Things.
# Table of Contents
## Laboratory Activities:
1. Laboratory Activity 1: Working with Digital Signals
   </br>
   - **Overiew:** This activity demonstrates how to program an Arduino microcontroller to control multiple lights automatically. Instead of writing separate instructions for every single light, this project uses    smart programming shortcuts (called Arrays and Loops) to handle a sequence of 5 LEDs efficiently.
2. Laboratory Activity 2: Working with Analog Signals
   </br>
   - **Overview:** This activity is an Arduino-based circuit designed to control a series of five LEDs sequentially. It serves as an introduction to IoT concepts, demonstrating how to use arrays and loops to manage multiple hardware outputs efficiently.
3. Laboratory Activity 3: Working with Sensors
   </br>
   - **Overview:** This activity involves the creation of a Fire Sensor Simulation using an Arduino Uno. The system is designed to monitor environmental conditions, specifically light and temperature to determine if a threshold has been reached that indicates a potential fire or hazard.
4. Laboratory Activity 4: Arduino Serial Connection
   </br>
   - **Overview:** This activity demonstrates a sensor-driven automation system using an Arduino Uno. The system monitors ambient light levels using a Photoresistor (LDR) and triggers a visual alert (blinking LED) when a specific brightness threshold is met. It also features an interactive serial interface, allowing a user to manually override and stop the blinking through text commands.
5. Laboratory Activity 5: Receiving Serial Connection using Arduino from Python
    </br>
   - **Overview:** This activity establishes a bi-directional communication system between a computer (running Python) and a microcontroller (Arduino). The system is designed to allow a user to remotely control three LEDs (Red, Green, and Blue) via a Command Line Interface (CLI).
6. Laboratory Activity 6: Bidirectional Control using Arduino and Python
    </br>
   - **Overview:** This activity establishes a bidirectional communication loop between an Arduino microcontroller and a Python script running on a computer. The system functions as a "feedback loop" where physical interactions on the Arduino (button presses) are sent to the computer for processing, and the computer sends commands back to the Arduino to control hardware outputs (LEDs).
7. Laboratory Activity 7: Controllling Arduino using FastAPI
    </br>
   - **Overview:** This activity establishes a bi-directional communication system between a web server (FastAPI) and hardware (Arduino) wherein you can control three LEDs (Red, Green, Blue) via HTTP requests or physical buttons, and the system reports physical button presses back to the Python console.
## Laboratory Examinations:
- Midterm Laboratory
  </br>
  -- **Overview:** This project is a Smart Light Monitoring System that measures ambient light intensity using a photoresistor. Based on the light levels, it activates specific status LEDs (Green, Yellow, Red) to indicate the environment (Cloudy, Normal, or Bright Sunlight). The system features a serial interface that allows users to switch between Automatic and Manual modes, and dynamically adjust threshold values while in Manual mode.
- Finals Laboratory
  </br>
  -- **Overview:** This project creates a physical interface for a web-based system. It consists of a hardware component (Arduino) that detects a physical button press and a software gateway (Python) that translates that physical action into a web request. When a user pushes a button on the hardware, the system identifies a specific "Group Number" and toggles a remote LED via a REST API.

# Technology Tools Used
1. Hardware: Arduino Kits
   </br>
   - Arduino Board (R3, R4)
   - LED Pins
   - Photoresistor
   - Temperature Resistor
   - Piezzo Buzzer
   - Push Buttons
2. Firmware: C++ (Arduino IDE)
3. Software: Python 3.13 (Visual Studio Code)
   - Libraries:
     </br>
     - Serial (Arduino)
     - Pyserial
     - FastAPI
     - Requests

# Each submitted laboratory contains the following:
## Files
1. Arduino Code Sketch Files (*.ino)
2. Python Code Files
3. Tinkercad Circuit Simulation
## References
### Website links
- A PDF files with compiled websites opened and used as reference.
### Generative AI
- The model of AI that has been used
- The transaction ID or the conversation used

# Contributors
## Activity 1-4
- Arrojo, Betina B.
- Mariano, Jamil S.
- Mendez, Rachelle Yazmhine C.
## Activity 5-7
- Ambong, Jemuel Chris N.
- Arrojo, Betina B.
- Dellosa, Keren G.
- Magma, John Harold R.
- Mariano, Jamil S.
- Mendez, Rachelle Yazmhine C.
- Pascual, Audric P.
