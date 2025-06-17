This repository contains a set of beginner-friendly electronics projects developed using Arduino Uno. Each project demonstrates core concepts like digital output, PWM, counters, and 7-segment display multiplexing. The tasks were completed as part of the Electronics & Automation domain of Project Kalpana.

📁 Project Overview
1️⃣ LED Brightness Control using Arduino
Objective: Control the brightness of an LED using a button, cycling through three levels – low, medium, and high.

🔩 Components:
Arduino Uno

1 × LED

1 × Push button

2 × 1KΩ resistor

Jumper wires

🔌 Circuit:
LED anode → Pin 9 (via 220Ω resistor)

LED cathode → GND

Button between Pin 11 and GND

⚙️ Working:
Each button press cycles the brightness level:

Low brightness

Medium brightness

Full brightness
Then loops back to low.

Brightness controlled using analogWrite() on PWM pin.


2️⃣ 4-Bit LED Up Counter
Objective: Build a binary up-counter from 0 to 15 using 4 LEDs to represent 4 bits.

🔩 Components:
Arduino Uno

4 × Red LEDs

4 × 220Ω resistors

Jumper wires

🔌 Circuit:
LEDs connected to Arduino pins 0, 1, 2, 3 through resistors.

LED cathodes connected to GND.

⚙️ Working:
Arduino increases a variable from 0 to 15.

Binary form is shown on LEDs.

Resets to 0 after reaching 15.


3️⃣ 2-Digit 7-Segment Counter (0 to 40 and Back)
Objective: Count from 0 to 40 and then back to 0 using two common cathode 7-segment displays, controlled using multiplexing.

🔩 Components:
Arduino Uno

2 × Common cathode 7-segment displays

9 × 220Ω resistors

Jumper wires

🔌 Circuit:
Segments A to G connected to Pins 2–8.

Digit control (common cathode) pins connected to Pins 9 and 10.

Displays share segment pins; only one is turned on at a time via multiplexing.

⚙️ Working:
Number increments from 0 to 40 and then decrements to 0 in a loop.

Number is split into tens and ones, shown alternately with a small delay.

Uses digitalWrite() to multiplex the digits quickly enough to appear constant.



