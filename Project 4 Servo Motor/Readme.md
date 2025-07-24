🚀 Servo Motor Angle Sweep using Arduino 
This project demonstrates how to control a servo motor using an Arduino Uno in Tinkercad. The servo rotates from 0° to a specified angle X°, pauses, and then returns smoothly back to 0°. This type of motion is commonly used in robotic arms, door openers, and automation mechanisms.

🧾 Objective
Control a servo motor to sweep from 0° to X° and back to 0° using Arduino.
Understand servo angle positioning with the Servo.h library.

🔩 Components Required
| Component    | Quantity       |
| ------------ | -------------- |
| Arduino Uno  | 1              |
| Servo Motor  | 1              |
| Breadboard   | 1 *(optional)* |
| Jumper Wires | 3              |

🔌 Circuit Connections
| Servo Motor Wire       | Connects To       |
| ---------------------- | ----------------- |
| 🟥 Red (VCC)           | Arduino **5V**    |
| ⬛ Brown/Black (GND)    | Arduino **GND**   |
| 🟧 Orange/Yellow (PWM) | Arduino **Pin 9** |

⚙️ How It Works
The Servo.h library enables precise control of servo motors.
The servo is attached to pin 9 using myServo.attach(9).
The program:
Sweeps the servo from 0° to X°.
Pauses briefly at X°.
Returns from X° to 0°.
delay(15) is used for smooth motion.
The loop repeats infinitely.

🧠 Arduino Code
```
#include <Servo.h>

Servo myServo;  
int angle = 0;    

void setup() {
  myServo.attach(9);  // Attach servo signal wire to pin 9
}

void loop() {
  int X = 90;  // User defined angle 

  if (X > 180) {
    X = 180;
  }

  // Rotate from 0 to X
  for (angle = 0; angle <= X; angle++) {
    myServo.write(angle); // Update servo angle
    delay(15);
  }

  delay(500); // Pause at X°

  // Rotate back from X to 0
  for (angle = X; angle >= 0; angle--) {
    myServo.write(angle);
    delay(15);
  }

  delay(1000); // Pause before next cycle
}
```

Simulation Link-
[Click Here](https://www.tinkercad.com/things/czv62yr0VAm-servo/editel?returnTo=%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=EEhVH_v-vsOW-KkSzvtoMpPi-h7yPVmf1ncIh2To780)
