# Laboratory Activity 3: Working with Sensors
## Overview
</br>
This activity involves the creation of a Fire Sensor Simulation using an Arduino Uno. The system is designed to monitor environmental conditions, specifically light and temperature to determine if a threshold has been reached that indicates a potential fire or hazard.

## Code Structure
- **Initialization:** Uses #define  to assign names to pins: notifyPin (12), thermistor (A0), and photoResistor (A2); also sets the threshold constraints, lightLimit (220) and tempLimit (50) to define both limits in temperature and light.
- **Sensor Functions**
  - **brightnessReading()**: Reads the photoresistor value. If the value exceeds lightLimit, it returns 1 (true); otherwise, 0 (false).
  - **temperatureReading()**: Reads the thermistor. It uses the map() function to convert the raw analog signal (0-1023) into a readable Celsius temperature (-40 to 125). It returns 1 if the temperature exceeds tempLimit.
- **Loop Logic**
  - **Conditional:** The alarm triggers only if brightnessValue AND temperatureValue are both true.
  - **Alarm:** If triggered, the code blinks the LED/Buzzer on/off with 1-second delays.
  
## Hardware Setup
- **Microcontroller:** Arduino Uno (R3)
- **Components**
  - **Input Sensors:** Temperature Sensor (TMP36); Photoresistor (LDR)
  - **Output Components:** Piezzo Buzzer; LED Pin (Red), resistors for the LED and Photoresistor
- **Breadboard and Jumper Wires**
## Project Flow
- **Monitoring:** The system continuously reads data from the temperature sensor and the light sensor.
- **Data Processing** The raw data from the temperature sensor is mathematically converted into degrees Celsius. Both sensor readings are compared against their pre-set limits (50°C for temp, 220 for light).
- **Feedback**
  - **Safe State:** If the area is dark or cool (or both), the system does nothing; the buzzer and LED remain OFF.
  - **Alarm State:** If the sensors detect that it is both bright (Fire light) AND hot (Fire heat), the system activates Pin 12.

## Reference
- [PDF File with compiled website links](https://github.com/btna-aroho/Internet-of-Things-Portfolio/blob/main/Laboratory%20Activities/Laboratory%20Activity%203/Act3-Reference.pdf)

## Contributors
**Leader:** Arrojo, Betina B.
### Members:
- Mariano, Jamil S. (98)
- Mendez, Rachelle Yazmhine C. (99)
