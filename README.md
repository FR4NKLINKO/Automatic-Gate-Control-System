🚪 SmartGate
Arduino Automatic Gate Control System

<p align="center">
<b>Smart • Automatic • Secure</b>
</p>

<p align="center">
An Arduino-based automatic gate system controlled by an infrared remote and equipped with a PIR motion sensor for enhanced safety.
</p>

📖 About the Project

SmartGate is an automatic gate control system built using an Arduino UNO. The project uses two servo motors to simulate the opening and closing of a double-leaf gate.

The system can be controlled remotely using an infrared (IR) remote controller. Additionally, a PIR motion sensor monitors movement near the gate and automatically stops the gate while it is moving if motion is detected.

The project also implements smooth servo movement, allowing the gate to open and close gradually instead of moving instantly.

⚙️ Features
🎮 IR Remote Control – Open, close, pause and resume the gate using the POWER button.
🚶 Motion Detection – PIR sensor detects movement near the gate.
🛑 Safety Stop – Gate movement is interrupted when motion is detected.
🔄 Pause & Resume – Stop the gate at any position and resume movement in the selected direction.
⚡ Smooth Movement – Servo motors move gradually, one degree at a time.
💡 LED Indicator – LED indicates whether the gate is currently moving.
🔧 Dual Servo Control – Two servos operate simultaneously to simulate a double-leaf gate.
🧰 Components
Component	Quantity
Arduino UNO	1
Servo Motor SG90	2
PIR Motion Sensor	1
IR Receiver	1
IR Remote Controller	1
LED	1
Resistor	1
Jumper Wires	As needed
🔌 Pin Configuration
Component	Arduino Pin
Servo 1	D3
Servo 2	D5
IR Receiver	D10
LED	D12
PIR Sensor	D4
🧠 How It Works

The system operates using a state-based control mechanism.

Operating States
State	Description
0	Gate closed
1	Gate open
4	Gate opening
5	Gate closing
6	Gate paused
Control Logic
Pressing the POWER button starts opening or closing the gate.
Pressing POWER again while the gate is moving pauses both servos.
Pressing POWER after pausing resumes movement in the previously selected direction.
When the gate reaches its target position, the system automatically changes to the appropriate final state.
If the PIR sensor detects movement while the gate is moving, the system immediately pauses the gate.
The LED lights up whenever the gate is in motion.
📐 Gate Positions
Gate Position	Servo 1	Servo 2
Closed	0°	180°
Open	90°	90°
Paused	Current position	Current position
💻 Technologies
Arduino C++
Arduino UNO
Servo.h
IRremote.hpp
PIR Motion Detection
State Machine Logic
📚 Required Libraries

Install the following libraries using the Arduino IDE Library Manager:

Servo – Servo motor control.
IRremote – Infrared remote communication.
🚀 Installation
Clone this repository:
bash
git clone https://github.com/YOUR-USERNAME/SmartGate.git

Open the .ino file in Arduino IDE.
Install the required libraries.
Connect all components according to the pin configuration.
Select Arduino UNO as the target board.
Upload the program to the Arduino.
📸 Project Preview

Add photos of your circuit, wiring diagram and working prototype here.

text
SmartGate/
│
├── SmartGate.ino
├── README.md
└── images/
    ├── circuit.png
    └── prototype.jpg

🔮 Future Improvements
Add automatic gate closing after a configurable delay.
Introduce obstacle detection in both opening and closing directions.
Add an LCD or OLED display for system status.
Implement adjustable servo movement speed.
Add Bluetooth or Wi-Fi control.
Introduce configurable remote control buttons.
👨‍💻 Author

Created as an Arduino electronics and programming project.

<p align="center">
<b>SMARTGATE</b>
<br>
<i>Making gate automation simple.</i>
</p>
