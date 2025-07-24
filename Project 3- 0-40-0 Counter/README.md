🔢 2-Digit 7-Segment Counter (0 to 40 and Back)
This Arduino project demonstrates how to count from 0 to 40 and back to 0 using two common cathode 7-segment displays and multiplexing. The project teaches binary-to-decimal conversion, display multiplexing, and timing using Arduino.

🎯 Objective
To display a number that continuously increments from 00 to 40 and then decrements back to 00 using two 7-segment displays, controlled efficiently through multiplexing with Arduino Uno.

🔧 Components Required
| Component                        | Quantity | Description                     |
| -------------------------------- | -------- | ------------------------------- |
| Arduino Uno (or compatible)      | 1        | Microcontroller board           |
| Common Cathode 7-Segment Display | 2        | To display tens and ones digits |
| 220Ω Resistors                   | 9        | Limits current to segment LEDs  |
| Jumper Wires                     | 10+      | For electrical connections      |
| Breadboard (optional)            | 1        | For clean prototyping           |

🛠️ Circuit Connections
| Segment | Arduino Pin |
| ------- | ----------- |
| A       | 2           |
| B       | 3           |
| C       | 4           |
| D       | 5           |
| E       | 6           |
| F       | 7           |
| G       | 8           |
💡 All segment pins are shared between the two displays.

🔌 Digit Control (Common Cathode)
| Digit | Arduino Pin |
| ----- | ----------- |
| Ones  | 9           |
| Tens  | 10          |
Only one display is active at a time to save on I/O pins—this is called multiplexing.

⚙️ Working Principle
The counter starts at 0, increments up to 40, and then counts down back to 0.
Each number is split into tens and ones digits.
The digits are shown one after the other very fast (every 5 ms), creating the illusion that both are on at the same time.
Multiplexing is used to control two displays using only 7 segment pins and 2 control pins.

📄 Arduino Code
```// Segment pins (A-G)
const int segmentPins[7] = {2, 3, 4, 5, 6, 7, 8};

// Common cathode digit control pins
const int digitPins[2] = {9, 10};

// Digit patterns for 0–9 (common cathode)
const byte digits[10][7] = {
  {1,1,1,1,1,1,0}, // 0
  {0,1,1,0,0,0,0}, // 1
  {1,1,0,1,1,0,1}, // 2
  {1,1,1,1,0,0,1}, // 3
  {0,1,1,0,0,1,1}, // 4
  {1,0,1,1,0,1,1}, // 5
  {1,0,1,1,1,1,1}, // 6
  {1,1,1,0,0,0,0}, // 7
  {1,1,1,1,1,1,1}, // 8
  {1,1,1,1,0,1,1}  // 9
};

int count = 0;
bool up = true;

void setup() {
  for (int i = 0; i < 7; i++) pinMode(segmentPins[i], OUTPUT);
  for (int i = 0; i < 2; i++) pinMode(digitPins[i], OUTPUT);
}

void loop() {
  for (int i = 0; i < 100; i++) {  // Refresh display 100 times (~1s)
    displayNumber(count);
  }

  if (up) {
    count++;
    if (count >= 40) up = false;
  } else {
    count--;
    if (count <= 0) up = true;
  }
}

void displayNumber(int num) {
  int tens = num / 10;
  int ones = num % 10;

  // Show tens digit
  digitalWrite(digitPins[1], HIGH); // Turn off other digit
  showDigit(tens);
  digitalWrite(digitPins[0], LOW);  // Enable tens digit
  delay(5);
  digitalWrite(digitPins[0], HIGH); // Disable after display

  // Show ones digit
  digitalWrite(digitPins[0], HIGH); // Turn off other digit
  showDigit(ones);
  digitalWrite(digitPins[1], LOW);  // Enable ones digit
  delay(5);
  digitalWrite(digitPins[1], HIGH); // Disable after display
}

void showDigit(int digit) {
  for (int i = 0; i < 7; i++) {
    digitalWrite(segmentPins[i], digits[digit][i]);
  }
}
```
🧠 Code Breakdown
| Code Segment                   | Purpose                                  |
| ------------------------------ | ---------------------------------------- |
| `digits[10][7]`                | Segment patterns for digits 0–9          |
| `displayNumber(count)`         | Splits number into tens and ones digits  |
| `showDigit(digit)`             | Activates the correct segments for digit |
| `digitPins[0]`, `digitPins[1]` | Control which 7-segment digit is active  |
| `delay(5)`                     | Briefly displays one digit at a time     |
| `if (count >= 40) up = false;` | Reverse direction after 40               |
| `if (count <= 0) up = true;`   | Reverse again when reaching 0            |


TinkerCad simulation-
[Click Here](https://www.tinkercad.com/things/4TbkbEZ0yJr-1-40-counter/editel?returnTo=%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=6PwEtH3PXzsFTEIUenwJ8GPBYpLZ3RQRwTf2-e6AbQo)
