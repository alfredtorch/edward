# Electronics

## Green House - Terra
This board is design to interact with your agricultural setup and start controlling actuators to help producing food.

Features:
* ESP32-based
* Tasmota and Esphome Compatible
* * Many PIN configuration possible (Solder Jumper)
* Many Vcc Configuration possible (Solder Jumper) with On Board Power Regulator 
* Open Source


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

If an component (ex. Servo) is present in different voltage leveles, means that it can be solder jumped to a single source (ex. 5V).

### Version

| Model | Notes |
| ---- | ---- |
| FishTankController V1 | Issue Flow Meter, 4 On-Board Load Power Switch (DC Avoiding 230V) |
| GreenHouse V1 | Issue Flow Meter, 4 External Power Control (AC&DC), Sonar |
| Fishtank | Integrate Library for Counter, 4 On Board Mosfet |

## Helios
This design allows you to tweak all the different light levels your plant deserves, while keeping everything cold. It uses a third-party LED circuit but allows you to build your own.
Features:
* ESP8266-based
* Tasmota and Esphome Compatible
* Open Source
* On Board Power Regulator
* Pluggable LED Drivers 
* Water Cooling Control and Sense

<p align="center">
<img width="870" alt="image" src="https://github.com/user-attachments/assets/0119ccfe-9abe-4433-8821-5196335cd68a">
</p>

On-Board LEDs help 
### Components
| PWM Label | Corresponding Label | PWM Label | Corresponding Label |
|-----------|---------------------|-----------|---------------------|
|ADC121C021   | ADC for  Turbine Temperature NTC       | EMC2101      | Fan Controller & Tach Monitor    |
|DS1683S      | Event Counter for Water Flowmeter                 | PCA9685      | PWM LED and Power Switch       |
|PCA9685      | PWM LED and Power Switch                  | LTC4311_SC70 | Improving I2C Stability (not populated)       |
|TMP1075DGKR5 | On Board Temperature Sensor                  | Smart Switch  | Type ... Load Ratings |
|PT4115       | LED Driver        |  ESP-01 | MCU Exist in ESP8266 and ESP32 | |


I2C Device Address Selection are design with solder jumpers. 

### Pinout 
| Pin   | Controls | Pin   | Controls | Pin   | Controls |Pin   | Controls |
|-------|----------|-------|----------|-------|----------|-------|----------|
| PWM0  | M4 Load  | PWM6  | LED 6    | PWM12 | Servo      | IO0 | SDA from MCU |
| PWM1  | M3 Load  | PWM7  | LED 5    | PWM13 | Error LED  | IO2 | SCL from MCU
| PWM2  | M2 Load  | PWM8  | LED 1    | PWM14 | Status LED | RST | Reset Button MCU |
| PWM3  | M1 Load  | PWM9  | LED 2    | PWM15 | Fan PWM | |
| PWM4  | LED 11   | PWM10 | LED 3    | WTemp LED | ADC121 Alarm     |
| PWM5  | LED 7    | PWM11 | LED 4    | WTach LED | DS16883S+ Alert  |

If an EMC2101 is mounted J15 should be not connected, in order to isolate PWM15 for interferring.

L1-8
L2-9
L3-10
L4-11
L5-7
L6-6
L7-5
L8-4

M1-3
M2-2
M3-1
M4-0

Servo-12
Fan (J)-15

 14
Error-13

 : 
WTach LED : 
Temp LED : TMP1075 OS

 

### ToDo
DS1682_Arduino.ino


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
<img width="870" alt="image" src="https://github.com/user-attachments/assets/d610eeb9-df20-4d0e-8b37-351e8e14251b">
</p>


## 8 SSR Rebel Channel

This design allows you to control and dimm your AC appliances. For a growtank this can be light output and for an irragation control valve 
Applying phase dimming to an unsupported appliance may destroy it. Carefull checking and handling is required while using the device.

all the different light levels your plant deserves, while keeping everything cold. It uses a third-party LED circuit but allows you to build your own.

Features:
* ESP32-based
* Tasmota and Esphome Compatible
* 8 Channel Phase dimming of AC Loads (0-100%) with dedicated Schmitt-Trigger for stable operations
* On Board ACDC Power Supply
* AC Current Monitor
* GUI with Display and Encoder

<p align="center">
<img width="800" alt="image" src="https://github.com/user-attachments/assets/1355ee44-3ea0-4316-8259-bdd46db87ab6">
</p>


### Pinout
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
<img width="800" alt="image" src="https://github.com/user-attachments/assets/cc561315-b2fe-48dc-a08d-927bb0633771">
</p>

# [Components](Components.md)
One design goal is to easy intergrate new components without needing to go back to a breadboard design. These components should be mainly be COTS (Custon-Off-The-Shelf) goods for easy and cost efficient sourcing.
A detailed overview is provided. These integrations can result direct on-board or request some addiditionnal PCB designs [available in the Hardware Repository](/Hardware/).

<p align="center">
<img width="800" alt="image" src="https://github.com/user-attachments/assets/2869c10f-52cb-4eb7-b3a5-28e97be0c340">
</p>


|Model|Integrate|Circuit|Notes|
|----|----|---|---|
|DC Load|Motors, pumps|Helio, GreenHouse v1 on-board - v2 external|Blablabla|
|AC Load|Motors, Lights, ...|SSR Rebel Fighter|Blabla|



