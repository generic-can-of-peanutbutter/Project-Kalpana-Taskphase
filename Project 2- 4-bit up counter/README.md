***4 BIT UP COUNTER***

 Objective
The goal of this project is to build a simple 4-bit upcounter using an Arduino UNO and LEDs. The counter will increment from 0000 (decimal 0) to 1111 (decimal 15) in binary, displaying each binary number using 4 LEDs. This is a great introductory project for learning digital electronics and binary number systems.
| Component     | Quantity | Description                                        |
| ------------- | -------- | -------------------------------------------------- |
| Arduino UNO   | 1        | Microcontroller board                              |
| Red LED       | 4        | Used to display binary count                       |
| 220Ω Resistor | 4        | Limits current to protect the LEDs                 |
| Jumper Wires  | 8+       | For electrical connections                         |
| Breadboard    | Optional | For easier prototyping (not used in current setup) |


 Circuit Description
In this setup:

4 LEDs are used to represent a 4-bit binary number (from bit 0 to bit 3).

Each LED is connected in series with a resistor to protect the LEDs from overcurrent.

The anode (+) of each LED is connected to Arduino digital pins 0,1,2and 3.

The cathode (−) of each LED is connected to GND on the Arduino.


Working Principle
The Arduino increments a variable count from 0 to 15.

For each value, the corresponding binary is output to the 4 LEDs.

Once it reaches 15 (1111), it resets back to 0 (0000).

A short delay is added for visible transition between states.

Tinkercad simulation-
https://www.tinkercad.com/things/fRO8G9j7Lw7-4-bit-upcounter/editel?returnTo=%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=op_Bbg1AW_Iwl3wZFaysurJuo0CwV1ZI7xx3nmVTbQY
