# Arduino HT16K33 7-Segment Counter

This project uses an **HT16K33-based 7-segment display** to count from 0 to 40 and then back to 0 using an **Arduino**.

## 🛠️ Hardware Required

- Arduino UNO (or compatible board)
- HT16K33 4-digit 7-segment display (e.g. Adafruit 0.56" 4-Digit 7-Segment Display w/I2C Backpack)
- Jumper wires
- Breadboard (optional)

## 🔌 Circuit Connections

The HT16K33 uses **I2C communication**, which requires only 2 wires:

| HT16K33 Pin | Arduino UNO Pin |
|-------------|-----------------|
| GND         | GND             |
| VCC         | 5V              |
| SDA         | A4              |
| SCL         | A5              |

> Note: For ESP32, SDA is usually GPIO 21, and SCL is GPIO 22.

## 📦 Arduino Libraries Used

Make sure to install the following libraries via the **Arduino Library Manager**:

- `Adafruit GFX Library`
- `Adafruit LED Backpack Library`
- `Wire` (comes pre-installed)

## 🧾 Code Functionality

- Displays numbers from `0` to `40` and then back to `0`.
- Each number is displayed for `500 ms`.
- Uses the I2C address `0x70` (default for HT16K33).

## 💻 How to Run

1. Connect the display as per the wiring table.
2. Open the Arduino IDE.
3. Install required libraries if not already installed.
4. Upload the code to the Arduino.
5. Watch the display count from 0 → 40 → 0 in a loop!

Simulation-

[Click Here](https://www.tinkercad.com/things/h5ieYjn5Lnx-glorious-snaget-albar/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=VuI9vMjuCC23srJum4rTrZ5KB4G0uaQiLnnUjFR17zo)

