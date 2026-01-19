# Laboratory Activity 4: Arduino Serial Connection
## Overview
</br>
This activity demonstrates a sensor-driven automation system using an Arduino Uno. The system monitors ambient light levels using a Photoresistor (LDR) and triggers a visual alert (blinking LED) when a specific brightness threshold is met. It also features an interactive serial interface, allowing a user to manually override and stop the blinking through text commands.

## Code Structure
- **Variable Declaration:** Sets constants for hardware, sensorPin (A0) for the input and LEDPin (8) for the output; this also defines brightnessThreshold of 220. If the light level crosses this number, the system reacts; and uses boolean flags (gaveCommand and blinking) to track the system's state—remembering if the user asked to stop or if the light is currently active.
- **Setup Function:** Configures communication with Serial.begin(9600) and sends a welcome message instructing the user to type 'stop' to disable the alarm.
- **Loop Logic**
  - **Sense:** Reads the raw sensor data (0-1023) and uses map() to convert it to a simpler 0-255 scale.
  - **Trigger:** If the light is high (>= 220) and the user hasn't stopped it yet, the blinking mode is set to true.
  - **Action:** If blinking is active, the LED toggles on and off rapidly (100ms delay).
  - **Listen:** The code constantly checks Serial.available(). If it receives text, it cleans it up (using trim() and toLowerCase()) and checks if the word is "stop". If it is, the system forces the LED off and prevents it from blinking again.

## Hardware Setup
- **Microcontroller:** Arduino Uno (R3)
- **Components**
  - **Input Sensor:** Photoresistor
  - **Output Component:** LED Pin (Red)
- **Breadboard and Jumper Wires**

## Project Flow
-**Monitoring:** The system continuously reads the ambient light level and prints the value to the Serial Monitor (e.g., "Brightness: 150").
- **Activation:** If you shine a bright light on the sensor (value exceeds 220), the LED on Pin 8 immediately starts blinking rapidly.
- **User Intervention:** While the LED is blinking, the user can open the Serial Monitor on their computer and type the word "stop".
- **Override:** The Arduino reads this text command. It immediately sets the gaveCommand variable to true, which breaks the blinking loop.
- **Shutdown:** The LED turns off and stays off, even if the light on the sensor remains bright, until the Arduino is reset.

## Reference
- [PDF File with compiled website links](https://github.com/btna-aroho/Internet-of-Things-Portfolio/blob/main/Laboratory%20Activities/Laboratory%20Activity%204/Act4-References.pdf)

## Contributors
**Leader:** Mendez, Rachelle Yazmhine
### Members
- Arrojo, Betina B. (99)
- Mariano, Jamil S. (100)
