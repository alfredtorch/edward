# Green House - Terra
The Green House - Terra board is designed to seamlessly integrate with your agricultural setup, enabling precise control over various actuators to enhance food production. This versatile board supports multiple devices and actuators, such as pumps and lights, making it ideal for diverse applications. While the fishtank version is highly accessible and beginner-friendly, the Green House - Terra platform offers unmatched versatility, capable of switching heavy loads running on mains power.

Features:
* ESP32-based
* Tasmota and Esphome Compatible
* Many PIN configuration possible (Solder Jumper)
* Many Vcc Configuration possible (Solder Jumper) with On Board Power Regulator 
* Open Source


<p align="center">
<img width="800" alt="image" src="https://github.com/alfredtorch/edward/assets/38537119/caf6568e-a54c-49b0-b28f-7a82f24329e7">
</p>

## Components
| Component                           | Description                                    | Component                       | Description                                    |
|-------------------------------------|------------------------------------------------|---------------------------------|------------------------------------------------|
| ESP32 MCU                           | The core microcontroller unit powering the board | QWIIC I2C Connector             | Simplifies the connection of sensors and modules |
| 4 Inputs for Water Level (Optical)  | Monitors water levels to ensure optimal conditions | Flow Meter (Hall Sensor)        | Measures water flow rate accurately             |
| Thermistor (Analog Temperature)     | Provides precise temperature readings          | 1-Wire Digital Temperature Sensor | Enables digital temperature monitoring         |
| Sonar Sensor (Distance)             | Measures distance using sonar technology       | 4 Solid State Relays (5V Level) | Controls high-power devices with reliability and safety |
| Fan (Speed Control, Tachometer Sense) | Manages airflow with speed control and tachometer feedback | 2 Power Outputs (PWM-DC)        | Drives power-hungry devices with PWM control    |
| LED Strips (5V Data Line)           | Controls LED lighting for various applications | Stepper Motor (28BYJ-48)        | Drives stepper motors for precise mechanical control |
| 2 GPIO Pins                         | General-purpose input/output pins for custom applications | 2 Limit Switches                 | Detects end positions or limits in mechanical movements |
| Air Sensor (Humidity, CO2, Temperature, Pressure) | Monitors air quality and environmental conditions | Multiple VCC Buses              | Provides flexible power distribution across multiple components |

## Pin-Out

| Pin  | Option 1      | Option 2      | Note                       |
|------|---------------|---------------|----------------------------|
| IO0  | Fan Signal Tacho | Stepper C     | GPIO Selector Solder Jumper |
| IO2  | LED Status    |               |                            |
| IO4  | RGB           | Solder Jumper |                            |
| IO5  | PIO3          | 5V Level - Mosfet Output |               |
| IO12 | Button Board  |               |                            |
| IO13 | PIO4          | RGB Pixel     | 5V Level - Load Output   |
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

_Note: If a component (e.g., a Servo) operates at different voltage levels, it can be configured to use a single power source (e.g., 5V) through the use of solder jumpers._

<p align="center">
<img width="500" alt="image" src="https://github.com/user-attachments/assets/43bde4f0-9ec0-491e-89ca-31dcf4b81e5b">
</p>

## ToDo
- [x] Use as Aquaponics Controll with ESPHOME (both fuelgauge and optical water)
- [ ] Test all configurations 

## Version

| Model                  | Notes                                                                 |
|------------------------|----------------------------------------------------------------------|
| FishTankController V1  | Flow Meter Issue, 4 On-Board Load Power Switches (DC, Avoids 230V)  |
| GreenHouse V1          | Flow Meter Issue, 4 External Power Controls (AC & DC), Sonar        |
| Fishtank               | Integrate Library for Counter, 4 On-Board MOSFETs                    |


<p align="center">
<img width="600" alt="image" src="https://github.com/user-attachments/assets/e97fcc15-910b-4755-9351-418b5c4119d3">
<br>
A working Green-House Controller running the cycle of our first station.
</p>

# Helios
This design allows you to tweak all the different light levels your plant deserves, while keeping everything cold. It uses a third-party LED circuit but allows you to build your own.
Features:
* ESP8266-based
* Pluggable LED Drivers 8 Channel + 1 external PWM 
* Tasmota and Esphome Compatible
* Open Source
* On Board Power Regulator
* Water Cooling Control and Sense (Flow and Temperature Meter)
* On-Board LEDs helps to notifity about the system health

<p align="center">
<img width="870" alt="image" src="https://github.com/user-attachments/assets/0119ccfe-9abe-4433-8821-5196335cd68a">
</p>

## Components

| Component     | Description                                                                 | Component         | Description                                                      |
|---------------|-----------------------------------------------------------------------------|-------------------|------------------------------------------------------------------|
| ADC121C021    | ADC for Turbine Temperature NTC                                             | EMC2101           | Fan Controller & Tach Monitor                                    |
| DS1683S       | Event Counter for Water Flowmeter                                           | PCA9685           | PWM LED and Power Switch                                         |
| PCA9685       | PWM LED and Power Switch                                                    | LTC4311_SC70      | Improving I2C Stability (not populated)                          |
| TMP1075DGKR5  | On Board Temperature Sensor                                                 | VNN7NV04PTR-E     | Smart Switch 4 Channel like  max 30V at 6A (Low Side)            |
| PT4115        | LED Driver IC Module                                                        | ESP-01            | MCU present in ESP8266 and ESP32                                 |

_Note: I2C device addresses are selectable with solder jumpers._

## Pinout 

| Pin   | Controls          | Pin   | Controls       | Pin      | Controls     | Pin   | Controls         |
|-------|-------------------|-------|----------------|----------|--------------|-------|------------------|
| PWM0  | M4 Load           | PWM6  | LED 6          | PWM12    | Servo        | IO0   | SDA from MCU     |
| PWM1  | M3 Load           | PWM7  | LED 5          | PWM13    | Error LED    | IO2   | SCL from MCU     |
| PWM2  | M2 Load           | PWM8  | LED 1          | PWM14    | Status LED   | RST   | Reset Button MCU |
| PWM3  | M1 Load           | PWM9  | LED 2          | PWM15    | Fan PWM      |       |                  |
| PWM4  | LED 11            | PWM10 | LED 3          | WTemp LED| ADC121 Alarm |       |                  |
| PWM5  | LED 7             | PWM11 | LED 4          | WTach LED| DS1683S Alert|       |                  |

_Note: If an EMC2101 is mounted, J15 should not be connected to isolate PWM15 and prevent interference._

## ToDo
- [X] 9 Channel, On-Board  + Alu Heat Sink Temperature, controlled by ESPHOM
- [ ] EMC2101 test
- [ ] Integrate DS1683S in ESPHOME
- [ ] Try DS1682 for Event Counter
- [ ] Write an advanced code (GUI - Scheduler for it)

<p align="center">
<img width="600" alt="image" src="https://github.com/user-attachments/assets/58766274-3675-435b-a5ba-21243c883404">
<br>
A working Helios setup emitting around 150 Watt of light output, water and air cooled. Mounted on a eurobox.
</p>

# 8 SSR Rebel Channel
This design allows you to control and dim your AC appliances. For a grow tank, this can be light output, and for an irrigation control valve. Applying phase dimming to an unsupported appliance may destroy it. Careful checking and handling are required while using the device.

This system provides all the different light levels your plant deserves while keeping everything cool. It uses a third-party LED circuit but allows you to build your own.

Features:
- **ESP32-based:** Built around the reliable and efficient ESP32 microcontroller.
- **Tasmota and ESPHome Compatible:** Easily integrates with popular home automation frameworks.
- **8 Channel Phase Dimming of AC Loads (0-100%):** Equipped with a dedicated Schmitt-Trigger for stable operations.
- **On-Board ACDC Power Supply:** Ensures stable power management.
- **AC Current Monitor:** Monitors the current to ensure safe and efficient operation.
- **GUI with Display and Encoder:** User-friendly interface for easy control and monitoring.

<p align="center">
<img width="800" alt="image" src="https://github.com/user-attachments/assets/1355ee44-3ea0-4316-8259-bdd46db87ab6">
</p>

## Components
| Component     | Description                                                                 | Component         | Description                                                      |
|---------------|-----------------------------------------------------------------------------|-------------------|------------------------------------------------------------------|
| AQG22212 or G3MB-202PL | SSR AC 2Amp No Zero Crossing                                       | Rotary Encoder            | Fan Controller & Tach Monitor                                    |
| WS29812       | Event Counter for Water Flowmeter                                           | OLED           | PWM LED and Power Switch                                         |
| Jack 3,5mm Current       | Circuit for reading SCT-013                                      | IR Receiver      | Receives commands from IR Remote Control                       |
| DS18b20       | On-board or JST Plug for temperature reading                                | Button & Potentiometer      | User Interface and analog read                    |


## Pinout
| Pin | Controls | Pin | Controls | Pin | Controls |
|-----------|---------------------|-----------|---------------------| -----------|---------------------|
|  IO26     | SSR1                  | IO39      | Analog            | IO22       | SCL                 |
| IO18      | SSR2                  | IO35      | InfraRed          | IO25       | SDA                 |
| IO19      | SSR3                  | PWM9      | ZeroCrossing      | IO13       | EncoderA            |
| IO23      | SSR4                  | IO33      | CurrentSignal     | IO36       | EncoderB            |
| IO17      | SSR5                  | IO02      | Temp              | IO4        | EncoderS            |
| IO16      | SSR6                  | IO32      | RGB               |            |                     |
| IO27      | SSR7                  | PWM13     | BTN               |            |                     |
| IO25      | SSR8                  |           |                   |            |                     |

Zero Crossing = can be used as main detector (binary state) JP2 connected or zero crossing phase detector (periodic trigger) JP2 blank).
<p align="center">
<img width="600" alt="image" src="https://github.com/user-attachments/assets/cc561315-b2fe-48dc-a08d-927bb0633771">
<br>
A working SSR 8 Rebel Controller controlling 6 LED Channel, 1 Waterpump and 1 Fan.
</p>

## ToDo
- [X] 8 Channel AC Phase Dimmed controlled by ESPHOME
- [ ] Current Clamp Monitor Not yet tested
- [ ] GUI components not yet tested

# [Components](Components.md)
One design goal is to easily integrate new components without needing to revert to a breadboard design. These components should mainly be COTS (Custom-Off-The-Shelf) goods for easy and cost-efficient sourcing. A detailed overview is provided. These integrations can result in direct on-board implementation or require additional PCB designs available in the [available in the Hardware Repository](/Hardware/).

<p align="center">
<img width="800" alt="image" src="https://github.com/user-attachments/assets/2869c10f-52cb-4eb7-b3a5-28e97be0c340">
</p>

