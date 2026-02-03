# Arduino Ultrasonic Distance Sensor — Arduino Uno R4 WiFi

Simple project that measures distance using an HC-SR04 ultrasonic sensor and prints results to the serial monitor. Example code is in `src/main.cpp`. Project is configured for PlatformIO via `platformio.ini`.

## Features
- Trigger HC\-SR04 and measure echo time
- Calculate distance in centimeters
- Print readings to Serial at 9600 baud

## Hardware
- `Arduino Uno R4 WiFi`
- HC\-SR04 ultrasonic sensor
- Jumper wires
- Breadboard (optional)
- USB cable

## Wiring
- `VCC` -> 5V
- `GND` -> GND
- `Trig` -> Digital pin 9
- `Echo` -> Digital pin 10

## Files
- `src/main.cpp` — main Arduino sketch
- `platformio.ini` — PlatformIO project configuration

## PlatformIO (recommended) — Windows / CLion
1. Install PlatformIO Core or the PlatformIO CLion plugin.
2. Ensure `platformio.ini` contains an environment for the Uno R4 WiFi (example):
    ```
    [env:uno_r4_wifi]
    platform = arduino
    board = arduino_uno_r4_wifi
    framework = arduino
    ```
3. Build and upload:
    - Build: `pio run -e uno_r4_wifi`
    - Upload: `pio run -e uno_r4_wifi -t upload`
4. Open serial monitor: `pio device monitor -e uno_r4_wifi -b 9600`

## CLion
- Use the PlatformIO plugin or configure a Run/Debug configuration that runs the `pio` commands above.
- Start the serial monitor from PlatformIO or use the `pio device monitor` command.

## Arduino CLI (alternative)
- Compile and upload using the correct FQBN for `Arduino Uno R4 WiFi`.
- Open serial monitor at 9600 baud.

## Usage
1. Upload firmware.
2. Open Serial Monitor at 9600 baud.
3. Read distance values printed periodically.

## Bug / Fix
The example `src/main.cpp` prints labels but not the numeric value. Replace the print lines with the following so the measured value is shown:

    Serial.print(distance);
    Serial.println(" cm");

## Troubleshooting
- Constant or zero readings: check wiring and pin assignments.
- Verify `echo` pin is connected to a digital input.
- Make sure sensor has clear line of sight.
- If using a 3.3V board, ensure the HC\-SR04 signal levels are compatible or use a level shifter.

## License
MIT License — see `LICENSE` for details.
