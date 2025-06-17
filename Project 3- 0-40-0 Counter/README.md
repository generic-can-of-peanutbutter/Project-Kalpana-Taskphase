 2-Digit 7-Segment Counter (0 to 40 and Back)

This Arduino project displays a number counting from 0 to 40 and then back to 0 using two **common cathode 7-segment displays**. The digits are displayed using **multiplexing** and controlled via digital pins.

 Hardware Components

- Arduino Uno (or compatible board)
- 2 x Common Cathode 7-Segment Displays
- 9 x 220Ω resistors
- Jumper wires

Circuit Connections-

Segment Pins (A to G):

| Segment | Arduino Pin |
|---------|-------------|
| A       | 2           |
| B       | 3           |
| C       | 4           |
| D       | 5           |
| E       | 6           |
| F       | 7           |
| G       | 8           |

> Note: These segment pins are shared by both 7-segment displays.

### Digit Control Pins (Common Cathode):

| Digit | Arduino Pin |
|-------|-------------|
| Ones  | 9           |
| Tens  | 10          |

> Only one display is turned on at a time (multiplexing) to reduce pin usage.

 How It Works

- The display shows a number that increases from 0 to 40 and then decreases back to 0 repeatedly.
- Multiplexing is used to control both displays with only 7 segment pins and 2 digit control pins.
- Each number is broken into tens and ones digits and displayed alternately with a small delay.

TinkerCad simulation-
https://www.tinkercad.com/things/4TbkbEZ0yJr-1-40-counter/editel?returnTo=%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=6PwEtH3PXzsFTEIUenwJ8GPBYpLZ3RQRwTf2-e6AbQo
