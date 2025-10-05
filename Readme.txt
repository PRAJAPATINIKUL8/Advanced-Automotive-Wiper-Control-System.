Automated Wiper Control System
A simulation of an automated vehicle wiper control system designed in MATLAB & Simulink. This system adjusts the wiper speed based on the intensity of rainfall, detected by a simulated rain sensor.

📝 Description
This project models a smart wiper system that eliminates the need for manual adjustment by the driver. The control logic, implemented using a Stateflow chart, processes the input from a rain sensor and actuates the wiper motor at different speeds (OFF, LOW, HIGH). The entire system is built and simulated within the Simulink environment.

The primary goal is to demonstrate a closed-loop control system for an common automotive application.

✨ Features
Automatic Mode: Wipers activate and adjust speed automatically based on simulated rain intensity.

Manual Override: A switch allows the user to manually select OFF, LOW, or HIGH speed modes.

State Control: Utilizes a Stateflow chart to manage the system's operational states efficiently.

Real-time Visualization: Scopes and displays show the current rain level, control mode, and resulting wiper speed.

🛠️ Software Requirements
To run this simulation, you will need:

MATLAB 2025a (or a compatible version)

Simulink Toolbox

Stateflow Toolbox

🚀 How to Run the Simulation
Clone or Download: Get a local copy of this project repository.

Open the Project: Launch MATLAB and navigate to the project's root directory.

Open the Simulink Model: Double-click the main Simulink file (e.g., WiperControlSystem.slx).

Run the Simulation:

Click the Run (▶) button in the Simulink Editor toolbar.

The simulation will start. You can interact with it in real-time.

Interact with the Model:

Use the Slider or Signal Builder block to change the 'Rain Intensity' value.

Toggle the 'Mode' switch to change between Automatic and Manual control.

Observe the output on the Scopes and Dashboard blocks to see how the wiper speed responds.

⚙️ Model Overview
The Simulink model is composed of three main subsystems:

Sensor (Input)

Simulates the rain sensor. A Slider allows you to manually vary the rain intensity from 0 (no rain) to 10 (heavy rain).

Controller (Logic)

The core of the system, this Stateflow chart contains the logic for both automatic and manual modes. It takes the rain intensity and mode selection as inputs and outputs the desired wiper speed state.

Automatic Logic:

Rain < 2: Wipers OFF

2 ≤ Rain < 6: Wipers LOW Speed

Rain ≥ 6: Wipers HIGH Speed

Actuator (Output)

Represents the physical wiper motor. It receives the command from the controller and generates a corresponding waveform, which is visualized in a Scope.

🤝 Contributing & Contact
Contributions, issues, and feature requests are welcome! Feel free to check the issues page or submit a pull request.

For any questions or suggestions, please contact:
Nikul Prajapati - prajapatinikul8@gmail.com