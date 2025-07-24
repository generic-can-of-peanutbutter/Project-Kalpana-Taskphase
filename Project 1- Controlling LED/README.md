💡 LED Brightness Control using Arduino
This project demonstrates how to cycle an LED through three brightness levels—Low, Medium, and High—using a push button. Each button press increases the brightness, and the cycle restarts after the highest level.

🔧 Components Used
1 × Arduino Uno
1 × LED
1 × Push button
2 × 1KΩ resistors (used for pull-down configuration, if needed externally)
Jumper wires

🛠️ Circuit Description
LED:
Anode (longer leg) → Connected to PWM Pin 9 via a 220Ω resistor
Cathode (shorter leg) → Connected to GND

Push Button:
One terminal → Connected to Digital Pin 11
Other terminal → Connected to GND

Internal pull-up resistor is enabled in the code (INPUT_PULLUP), so no external resistor is required

⚠️ Ensure that the button connects to GND when pressed to work correctly with INPUT_PULLUP.

⚙️ Working Principle
The LED brightness changes on each button press as follows:
First Press → Low brightness
Second Press → Medium brightness
Third Press → High brightness
Fourth Press → Back to Low

Brightness is controlled using the analogWrite() function on the PWM-enabled pin.

🧠 Code Explanation
The Arduino code uses a counter variable (count) to track the brightness level. Each button press increments this counter and wraps it back to 0 after reaching 2. A debounce delay ensures stable operation.
| Line / Block                        | Description                                                             |
| ----------------------------------- | ----------------------------------------------------------------------- |
| `const int ledPin = 9;`             | Assigns PWM pin 9 to the LED                                            |
| `const int buttonPin = 11;`         | Assigns pin 11 to the push button                                       |
| `pinMode(buttonPin, INPUT_PULLUP);` | Enables internal pull-up resistor (so button reads HIGH when unpressed) |
| `digitalRead(buttonPin)`            | Reads the current button state                                          |
| `if (buttonState == LOW && ...)`    | Detects new button press (rising edge logic)                            |
| `count++` / `if (count > 2)`        | Increments and cycles the brightness counter                            |
| `analogWrite(ledPin, value)`        | Sends PWM signal to control brightness                                  |


📄 Code Overview
```cpp
const int ledPin = 9;       // LED connected to PWM pin 9
const int buttonPin = 11;   // Button connected to pin 11

int count = 0;
bool lastButtonState = HIGH;

void setup() {
  pinMode(ledPin, OUTPUT);
  pinMode(buttonPin, INPUT_PULLUP); // Internal pull-up for button
}

void loop() {
  bool buttonState = digitalRead(buttonPin);

  if (buttonState == LOW && lastButtonState == HIGH) {
    count++;
    if (count > 2) count = 0;
    delay(200); // Debounce delay
  }

  lastButtonState = buttonState;

  // Set LED brightness based on count
  if (count == 0) {
    analogWrite(ledPin, 255);   // Low brightness
  } else if (count == 1) {
    analogWrite(ledPin, 100);  // Medium brightness
  } else if (count == 2) {
    analogWrite(ledPin, 0);  // High brightness
  }
}
```

Tinkercad Simulation
You can simulate and test the circuit using Tinkercad:
[Click Here](https://www.tinkercad.com/things/bKjHkQrKNRq-led-brightness-control/editel?returnTo=%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=7MSoEUGcPuuRr2TDVYyR6ZM_01KdrPbgD89l3kFken8)
