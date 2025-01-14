# Flood Detection and Alert System

## Overview
This project is a **Flood Detection and Alert System** that uses an ultrasonic sensor and a float sensor to monitor water levels and provide real-time alerts via SMS and phone calls. The system is powered by an Arduino microcontroller and a GSM module (SIM900) for communication.

## Features
- **Water Level Detection**: Measures the water level using an ultrasonic sensor.
- **Flood Risk Levels**:
  - **Low Risk**: Water level above 25 cm.
  - **Moderate Risk**: Water level between 10 cm and 20 cm.
  - **High Risk**: Water level below 10 cm.
- **Real-Time Alerts**:
  - Sends an SMS with the risk level.
  - Initiates a phone call to the predefined contact number.

## Components
- **Arduino Board**
- **SIM900 GSM Module**
- **Ultrasonic Sensor (e.g., HC-SR04)**
- **Float Sensor**
- Jumper Wires
- Power Supply

## Prerequisites
### Hardware
1. Connect the ultrasonic sensor:
   - **Trig Pin**: A1
   - **Echo Pin**: A0
2. Connect the float sensor to digital pin 12.
3. Connect the GSM module to pins 7 (RX) and 8 (TX).
4. Ensure proper power supply for the Arduino and GSM module.

### Software
- Install the Arduino IDE.
- Include the `SoftwareSerial` library (bundled with the Arduino IDE).

## Setup and Usage
1. Clone this repository:
   ```bash
   git clone <repository-url>
   ```
2. Open `flood_detection.ino` in the Arduino IDE.
3. Update the phone number in the `number` variable in the code:
   ```cpp
   String number = "+919744640750";
   ```
4. Upload the code to your Arduino board.
5. Power up the setup and monitor the Serial Monitor for logs.

## How It Works
1. The float sensor detects if water is present.
2. The ultrasonic sensor measures the water level.
3. Based on the distance:
   - Sends an SMS with the flood risk level.
   - Makes a phone call to the predefined contact number.
4. Logs the measured distance and risk level to the Serial Monitor.

## Code Explanation
- **Ultrasonic Sensor Function**:
  Measures distance by emitting ultrasonic pulses and calculating the time it takes for the echo to return.

- **SMS Sending Function**:
  Configures the SIM900 GSM module to send an SMS with the specified message.

- **Call Function**:
  Configures the SIM900 GSM module to initiate a phone call to the predefined number.

## Risk Levels
| Risk Level     | Distance (cm)   | Action                        |
|----------------|-----------------|-------------------------------|
| Low Risk       | > 25            | Send SMS and make a call.     |
| Moderate Risk  | 10 – 20        | Send SMS and make a call.     |
| High Risk      | ≤ 10           | Send SMS and make a call.     |

## Notes
- Ensure the GSM module is receiving adequate power and has a valid SIM card with SMS and call capabilities.
- Modify the code to adjust the risk thresholds if necessary.

## Contribution
Feel free to fork this repository and submit pull requests to improve the functionality or documentation.

## License
This project is licensed under the MIT License. See the `LICENSE` file for more details.

