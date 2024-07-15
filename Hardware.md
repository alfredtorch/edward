# Electronics

## Green House - Terra
With this device, you can easily interact with your agricultural setup and start controlling actuators to grow  
Features:
ESP32-based
Many configuration possible (Solder Jumper)
Tasmota and Esphome Compatible
Open Source
On Board Power Regulator
<p align="center">
<img width="800" alt="image" src="https://github.com/alfredtorch/edward/assets/38537119/caf6568e-a54c-49b0-b28f-7a82f24329e7">
</p>

| Pin  | Option 1      | Option 2      | Note                       |
|------|---------------|---------------|----------------------------|
| IO0  | Fan Signal Tacho | Stepper C     | GPIO Selector Solder Jumper |
| IO2  | LED Status    |               |                            |
| IO4  | RGB           | Solder Jumper |                            |
| IO5  | PIO3          | 5V Level - Mosfet Output |               |
| IO12 | Button Board  |               |                            |
| IO13 | PIO4          | RGB Pixel     | 5V Level - Mosfet Output   |
| IO14 | Limit 1       | Servo 1 / Sonar Trigger | GPIO Selector Solder Jumper |
| IO15 | Servo 2       | Stepper D     | GPIO Selector Solder Jumper |
| IO16 | Fan PWM       |               |                            |
| IO17 | 1-Wire        | Dallas 1 Wire Sensor |                    |
| IO18 | Turbine Tacho | Flow Meter    |                            |
| IO19 | PIO1          |               | 3V3 Level                   |
| IO21 | SDA           |               | 3V3 Level                   |
| IO22 | SCL           |               | 3V3 Level                   |
| IO23 | PIO2          |               | 5V Level                    |
| IO25 | Limit 1       | Stepper B     | GPIO Selector Solder Jumper |
| IO26 | Turbine Therm | Water Temperature |                        |
| IO27 | Servo 1 / Sonar Trigger | Stepper A | GPIO Selector Solder Jumper |
| IO32 | Fan Tacho     | Limit 2       | GPIO Selector Solder Jumper |
| IO33 | Limit 2       | Servo 2       | GPIO Selector Solder Jumper |
| IO34 | Water LEVEL 3 |               | Optical or physical switch  |
| IO35 | Water LEVEL 2 |               | Optical or physical switch  |
| IO36 | Water LEVEL 4 | Sonar Echo    | Optical or physical switch  |
| IO39 | Water LEVEL 1 |               | Optical or physical switch  |
| VIN1 | USB C, STEPPER, SERVO |       | Max 30V, Input of DCDC 5V & 3V3 - direct 5V |
| VIN2 | RGB, VFAN, MOSFET |           | Direct 5V                  |
| 5V   | RGB, STEPPER, SERVO, MOSFET, VFAN | |                     |
| 3V3  | SERVO, MCU    |               |                            |

### Version
| Model | Notes |
| ---- | ---- | 
| GreenHouse V1 | Issue Flow Meter, 4 External Power Control (AC-DC) |
| GreenHouse V2 | Issue Flow Meter, 4 External Power Control (AC-DC) |
| Fishtank | Issue Flow Meter, 4 On Board Mosfet |
## Helios

This design allows you to tweak all the different light levels your plant deserves, while keeping everything cold. It uses a third-party LED circuit but allows you to build your own.
Features:
- ESP8266-based
- Tasmota and Esphome Compatible
- Open Source
- On Board Power Regulator
- Pluggable LED Drivers 
- Water Cooling Control and Sense

### On-Board
|Feature|Notes|
|-----|----|
|Temperature Sensor|On Board and Heatsink|


### Pinout
| Pin  | Option 1      | Option 2      | Note                       |
|------|---------------|---------------|----------------------------|
| IO0  | Fan Signal Tacho | Stepper C     | GPIO Selector Solder Jumper |
| IO2  | LED Status    |               |                            |

8 Channel LED Driver
2 PWM Output
1 Water Flow + Temperature Meter

<p align="center">
<img width="800" alt="image" src="https://github.com/user-attachments/assets/910557bd-16e3-42e0-bf80-1276e8ef2b19">
</p>


## 8 SSR Rebel Channel
8 AC 2Amp Channel
<p align="center">
<img width="942" alt="image" src="https://github.com/user-attachments/assets/2f5ee228-50b8-4190-a45a-cc2ea2bf2bc4">
</p>

# Components
|Model|Integrate|Circuit|Notes|
|----|----|---|---|
|DC Load|Motors, pumps|Helio, GreenHouse v1 on-board - v2 external|Blablabla|
|AC Load|Motors, Lights, ...|SSR Rebel Fighter|Blabla|



