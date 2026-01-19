# Midterms Laboratory Examination
## Overview
This project is a Smart Light Monitoring System that measures ambient light intensity using a photoresistor. Based on the light levels, it activates specific status LEDs (Green, Yellow, Red) to indicate the environment (Cloudy, Normal, or Bright Sunlight). The system features a serial interface that allows users to switch between Automatic and Manual modes, and dynamically adjust threshold values while in Manual mode. The following features of this system is its Dual-Mode Operation:
- **Automatic Mode:** Uses pre-set values to decide when to switch lights.
- **Manual Mode:** Allows the user to type commands into the computer to customize the sensitivity thresholds dynamically.

## Code Structure
- **Global Variables & Enums:** Defines mode as either MANUAL or AUTOMATIC. This also sets defaults for every LEDs; for the greenLedPin (11), yellowLedPin (12), redLedPin (13), and photoresistorPin (A0).
- **Setup:** nitializes the Serial Monitor and prints instructions.
- **Loop Logic:** If the user typed anything, it calls checkSerialCommands() to see; for every 1000ms (1 second), it reads the light sensor, maps the value to a 0-100% scale, updates the LEDs, and prints a status report.
- **Command Parsing**
  - **checkSerialCommands():** Reads text input. If "MODE AUTO" is typed, it switches to automatic. If "SET LOW 30" is typed, it updates the low threshold variable.
  - **parseSetCommand():** Ensures user inputs are valid numbers (0-100) and that the low threshold is always lower than the high threshold.
- **LED Logic (updateLEDs):** Compares the current light % against the active thresholds. Turns on Green for low light, Yellow for medium, and Red for high light.

## Hardware Setup
- **Microcontroller:** Arduino Uno (R3)
- **Input Sensor:** Photoresistor; 10k resistor
- **Output Indicators:** 3x LED Pins
- **Breadboard and Jumper Wires**

## Project Flow
1. **Automatic Mode:** The system reads light intensity.
   - **Logic:**
     - If light is 0-40%: The Green LED turns on (Status: "Cloudy").
     - If light is 41-70%: The Yellow LED turns on (Status: "Normal").
     - If light is >70%: The Red LED turns on (Status: "Bright Sunlight").
3. **Manual Mode:** The user types MODE MANUAL. The system confirms "Mode changed to MANUAL".
   - **Customizing:**
     - The user types SET HIGH 90.
     - The system updates the highThreshold to 90.
     - The Red LED will only turn on if light exceeds 90% (making the system less sensitive to bright light).

## Reference
- Generative AI has been used in support for this project.
  - [Prompts used to transact with your selected Generative AI (Gemini 3 Pro)](https://docs.google.com/document/d/157kyq6bmzsTN36vueSw1yjSqWcjcszTZH0mbGn4xpRg/edit?fbclid=IwY2xjawPbCbFleHRuA2FlbQIxMQBzcnRjBmFwcF9pZAEwAAEeTUlNvU6Gpcb-66qT0IYlfkXpqsRzDDiRmT3COiCMYiVUaz4HigmyX_mfbxc_aem_fYdFLBUlg4bWl6ksFSEtWQ&tab=t.0)
  - [Transaction ID or the link of the conversation](https://gemini.google.com/share/a315dad58546?fbclid=IwY2xjawPbCaxleHRuA2FlbQIxMQBzcnRjBmFwcF9pZAEwAAEePrHxMt9c4O4s9BLVYmaooPjQN338RFgVbzGvcacyH2ZZGC3Db8D6mLMcZz8_aem_X9ZtbZsE6bZG-KBfe9laDQ)
## Contributors
- Arrojo, Betina B.
- Mariano, Jamil S.
- Mendez, Rachelle Yazmhine C.
- Osit, Eduardo
- Pascual, Audric P.
