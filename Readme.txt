Automatic Wiper System

Overview:
-----------
This project implements an automatic wiper system for vehicles using a rain sensor and a microcontroller (e.g., Arduino). The system detects rain intensity and automatically controls the speed of the wiper motor.

Components:
-----------
- Microcontroller (Arduino Uno or similar)
- Rain sensor module
- Relay module (to control wiper motor)
- Wiper motor
- Power supply

Basic Arduino Code Example:
---------------------------
const int rainSensorPin = A0;    // Analog pin for rain sensor
const int relayPin = 8;          // Digital pin for relay

void setup() {
    pinMode(relayPin, OUTPUT);
    Serial.begin(9600);
}

void loop() {
    int sensorValue = analogRead(rainSensorPin);
    Serial.print("Rain Sensor Value: ");
    Serial.println(sensorValue);

    if (sensorValue < 300) { // Heavy rain
        digitalWrite(relayPin, HIGH); // Wiper ON (fast)
        delay(500);
        digitalWrite(relayPin, LOW);
        delay(500);
    } else if (sensorValue < 600) { // Light rain
        digitalWrite(relayPin, HIGH); // Wiper ON (slow)
        delay(1000);
        digitalWrite(relayPin, LOW);
        delay(1000);
    } else {
        digitalWrite(relayPin, LOW); // Wiper OFF
    }
}

How it works:
-------------
- The rain sensor outputs an analog value based on rain intensity.
- The microcontroller reads this value and determines the rain level.
- Depending on the rain intensity, the wiper motor is activated at different speeds using a relay.

Note:
-----
- Adjust sensor thresholds as needed for your sensor.
- Ensure proper isolation and safety when interfacing with vehicle electronics.