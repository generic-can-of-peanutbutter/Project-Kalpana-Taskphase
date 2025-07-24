🔢 4-Bit Up Counter using Arduino
This project demonstrates how to build a simple 4-bit up counter using an Arduino UNO and LEDs. The counter increments from 0000 (decimal 0) to 1111 (decimal 15) in binary, with each bit displayed using an individual LED.
This is an excellent beginner-friendly project to understand binary number systems, bitwise operations, and digital logic implementation with microcontrollers.

🎯 Objective
To display a 4-bit binary counter (0 to 15) using 4 LEDs controlled by an Arduino UNO.

🔧 Components Required
| Component     | Quantity | Description                         |
| ------------- | -------- | ----------------------------------- |
| Arduino UNO   | 1        | Microcontroller board               |
| Red LED       | 4        | Displays the binary count           |
| 220Ω Resistor | 4        | Current-limiting resistors for LEDs |
| Jumper Wires  | 8+       | For making electrical connections   |
| Breadboard    | Optional | For easier and cleaner prototyping  |

🛠️ Circuit Description
4 LEDs represent the 4 bits (Bit 0 to Bit 3) of the counter.
Each LED is connected in series with a 220Ω resistor to limit the current.
LED anodes (+) are connected to Arduino digital pins 0, 1, 2, and 3.
LED cathodes (−) are connected to the GND pin of the Arduino.

⚠️ Note: If you're using Serial communication (like Serial.begin()), avoid using pins 0 and 1 for LEDs, as they are also the default RX/TX pins. You can replace them with other pins like 4, 5, 6, 7 if needed.

⚙️ Working Principle
The Arduino uses a for loop to increment a counter from 0 to 15.
For each value of the counter, the binary equivalent is calculated.
The binary bits are output to 4 digital pins, each controlling an LED.
The LEDs turn ON or OFF depending on whether the respective bit is 1 or 0.
After reaching 1111 (15), the counter resets to 0000.

Code-
```
// Define LED pins
int ledPins[4] = {0, 1, 2, 3};

void setup() {
  // Set LED pins as OUTPUT
  for (int i = 0; i < 4; i++) {
    pinMode(ledPins[i], OUTPUT);
  }
}

void loop() {
  for (int count = 0; count < 16; count++) {
    // Display count in binary using LEDs
    for (int i = 0; i < 4; i++) {
      int bit = (count >> i) & 1;
      digitalWrite(ledPins[i], bit);
    }
    delay(1000);  // Wait 1 second before next count
  }
}
```

🧠 Code Explanation
| Code Segment                           | Explanation                                  |
| -------------------------------------- | -------------------------------------------- |
| `int ledPins[4] = {0, 1, 2, 3};`       | Array to store the LED pin numbers           |
| `pinMode(ledPins[i], OUTPUT);`         | Sets each pin as an output pin               |
| `for (count = 0; count < 16; count++)` | Loop from 0 to 15 (4-bit counter)            |
| `(count >> i) & 1`                     | Bitwise operation to extract each bit        |
| `digitalWrite(ledPins[i], bit);`       | Turns ON/OFF LED based on bit value          |
| `delay(1000);`                         | Waits for 1 second before the next increment |




Tinkercad simulation-
[Click Here](https://www.tinkercad.com/things/fRO8G9j7Lw7-4-bit-upcounter/editel?returnTo=%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=op_Bbg1AW_Iwl3wZFaysurJuo0CwV1ZI7xx3nmVTbQY)
