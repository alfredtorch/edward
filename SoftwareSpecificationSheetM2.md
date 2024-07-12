# Milestone 2

## Current Prototype

### System Overview
The current prototype operates on an Ebb and Flow (Media-based) Aquaponics system, which requires a tidal mechanism to periodically raise and lower the water level. This process is crucial for oxygenating the roots and facilitating the filtration of nutrients in the plant tank.

<p align="center">
<img width="300" alt="image" src="https://github.com/user-attachments/assets/c0128cf4-0fa1-48f5-b6dd-2ed57a1dbdbe">
</p>

The prototype system is powered by Home Assistant with ESPHome running on a local Raspberry Pi . The main challenges faced by the current system include:
•	not a standalone system (Raspberrypi + Station Controller)
•	no option for easy remote monitoring of the system (NAT, DNS)
•	missing control options (regular self-calibration, failsafe mode)

<p align="center">
<img width="1000" alt="image" src="https://github.com/user-attachments/assets/687ef834-52ff-49b4-84f4-f12f1e8b8458">
</p>


### System Components


| Category     | Component                 | Description                              | Type                  |
|--------------|---------------------------|------------------------------------------|-----------------------|
| **Plant Tank** | 1x Falling Tide Pump      | Pumps from plants to fish                | SSR 220V - PIO        |
|              | 1x Water Level Top (PTT)  | Sense if the max. volume is reached      |                       |
|              | 1x Water Level Bottom (PTB) | Sense if the max. volume is reached    |                       |
|              | 1x Growing LED (optional) |                                          | SSR 220V - PIO        |
|              | 1x Water Temperature Sensor | Measure water temperature               | 1-Wire: DS18B20       |
| **Fish Tank**  | 1x Rising Tide Pump        | Pumps from fish to plant                 | SSR 220V - PIO        |
|              | 1x Flow Meter (optional)   | Turbine based                            | Interrupt PCTN²       |
|              | 1x Aquarium Heater         | Heat the water                           | SSR 220V - PIO        |
|              | 1x Air Pump                |                                          | 220V - NC/Always ON   |
| **Accessory** | 1x Gas sensor (Optional)   | For Air Monitoring                       | BME680                |
|              | 1x OLED Display (Optional) | For User Interface                       |                       |
|              | 2x Buttons (Optional)      | For User Interface                       |                       |


<img width="686" alt="image" src="https://github.com/user-attachments/assets/d7a0a320-0549-401e-9d89-1a303172b3ab">
