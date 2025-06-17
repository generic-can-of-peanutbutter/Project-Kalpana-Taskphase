LED Brightness Control using Arduino

 The brightness cycles through *three levels* — low, medium, and high — with each press of the button.

## Components Used-

- Arduino Uno
- 1 × LED
- 2 × 1KΩ resistor
- 1 × Push button
- Jumper wires

---

Circuit Description

- LED anode→ connected to Arduino Pin 9 (PWM) through a 220Ω resistor  
- LED cathode → connected to GND
- *Push button*:
  - One side to pin 11
  - Other side to GND


 Working-

- When the button is pressed:
  - First press → LED at low brightness
  - Second press → LED at medium brightness
  - Third press → LED at full brightness
  - Next press → cycles back to low brightness

- The brightness is controlled using analogWrite() on a PWM pin.

 
 Tinkercad Simulation

You can simulate and test the circuit using Tinkercad:

https://www.tinkercad.com/things/bKjHkQrKNRq-led-brightness-control/editel?returnTo=%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=7MSoEUGcPuuRr2TDVYyR6ZM_01KdrPbgD89l3kFken8
