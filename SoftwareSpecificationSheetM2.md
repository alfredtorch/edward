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

The current prototype remains on the following setup.
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

<p align="center">
<img width="686" alt="image" src="https://github.com/user-attachments/assets/d7a0a320-0549-401e-9d89-1a303172b3ab">
</p>

## Embedded Software Development
<p align="center">
<img width="685" alt="image" src="https://github.com/user-attachments/assets/2e55bfcc-7b53-4096-8870-adea2a558389">
</p>

The core goals of this software development phase are:
• Create the Edward Controller, which is responsible for maintaining optimal
conditions conducive to the health of aquatic life and plant growth.
• Design a User Interface that assists users in configuring their stations and
managing basic settings with ease.
• Facilitate remote connectivity through the IoT Integrator, enabling access
and control over the internet.
• Design a digital twin for virtual testing the system – Testing on a real station.

### Cycle Control
The Edward Controller's main function is to oversee the plant tank's automated tidal process. The software is engineered for reliability, crafted to maintain functionality in the face of technical challenges such as power outages and sensor errors. Operational scenarios are meticulously detailed within a truth table and in the analysis of Worst-Case Scenarios.

<p align="center">
<img width="341" alt="image" src="https://github.com/user-attachments/assets/72dd4478-94f7-4cf7-abf4-6ff370eb1828">
</p>

This table  represents the logical states of the sensors PTT and PTB, along with what each combination of states indicates.
| PTT | PTB | Indicates         |
|-----|-----|-------------------|
| 0   | 0   | BOTTOM (0%)       |
| 0   | 1   | MIDDLE            |
| 1   | 0   | Faulty Condition  |
| 1   | 1   | TOP (100%)        |

### System Inherit Requirements
 __Syphon__
 
Due to the falling pump's elevated position above the fish tank's outlet, a natural
siphon effect occurs, which allows the circuit to continue draining even when the
pump is not powered. This siphon effect could present a problem if it coincides with
the pump's rising cycle, as it would exacerbate the drainage and potentially trap the
system in a continuous loop and cause timeout errors. To mitigate this, the duration
of the low tide must be sufficiently long to ensure that the siphoning ceases before
the next cycle begins. The necessary duration of this delay is variable, as the
duration of the siphon effect is dependent on the height difference between the
bottom water level sensor and the drainage pump exit.

__Input Processing__

The inputs received from the water level sensors require filtering to ensure
accuracy. Implementing a debounce logic will mitigate the effects of transient
fluctuations, while taking the mean value from a series of observations will help to
nullify any disturbances caused by water movement. This approach is designed to
stabilize the readings and avoid false triggers that could result from wavegenerated
perturbations.

__Plants Illumination__

The system's lighting is managed by a straightforward scheduling mechanism,
which automates the grow lights, toggling them on and off as programmed.
Although the current iteration lacks the functionality to adjust light intensity, the
timing of the grow light is synchronized with the natural patterns of sunrise and
sunset. This synchronization provides the essential dark periods that plants require
for their rest and recovery during the night, ensuring a natural growth cycle is
maintained.

__Safety Mechansim__

| Situation             | Result               | Severity | Worst-Case Scenario Prevention                                                                                         |
|-----------------------|----------------------|----------|------------------------------------------------------------------------------------------------------------------------|
| Total drainage of the fish tank | Dead fish          | High     | Position rising pump above the min. water level. Limit operation time of the rising pump.                               |
| Tank Overflow         | Flooding the environment | High  | Install an overspill safeguard in the plant tank. Ensure fish tank capacity equals total water supplied.               |
| Not synced time       | Stressed plants due to excessive light | High | Synchronize system clock accurately (consider location-based settings).                                                 |
| Dryness in the plant tank | Stressed and dry plants | Medium | System can endure temporary dryness.                                                                                  |
| Power Failure         | Fish suffocation     | High     | Implement a heartbeat signal for regular checks. Automate system reboot when cycling stops.                            |
| Internet Failure      | No remote control and telemetry | Low  | Queue commands until connectivity is restored. Have a secondary access point as a fallback.                             |
| Pump Failure          | Nutrient imbalance   | Middle   | System can tolerate short-term pump failure.                                                                           |
| Hacker Attack         | Compromised system   | High     | Hardcoded vital function. Enable safety mechanisms to prevent unauthorized use.                                        |
| Overheat              | Dead Fish            | High     | 2 layers of safety (Edward control & Thermostat).                                                                      |


__Flow Meter (Optional)__

The integrated flow meter is essential for providing precise volume measurements
during the rising tide phase. It accurately gauges the total water capacity of the plant
tank. As plant roots grow and biomass increases, a natural reduction in the apparent
water capacity of the tank is expected. Therefore, a decrease in measured volume
over time can be indicative of healthy plant growth.
For routine monitoring, the flow meter serves as a diagnostic tool, offering
straightforward feedback—either confirming successful tank filling (OK) or detecting
issues (NOK). This feedback is crucial as it works with the water level sensors,
providing a secondary verification method to ensure that water-related sensors are
functioning properly.

__Water Heater (Optional)__

Aquarium heaters are typically equipped with built-in thermal controls, so no
special operations are required for this setup beyond the ability to turn the heater
on or off. For optimal functionality, it is crucial that the heater's operational state
persists through a power outage.
The water heater should operate within a defined temperature range for safety and
efficiency. If the water temperature falls below the minimum threshold, indicating
that the heater may not be functioning properly, the user should receive a
notification. Conversely, if the temperature exceeds the maximum limit, suggesting
excessive heating, the system should automatically turn off the heater and alert the
user to this condition.

### Tidal State Machine
During the current development phase, the system has been designed to manage
tidal controls through four distinct operational modes:
1. Calibration: Adjusts and sets the baseline parameters for tidal operations.
Normally occurs on first start and on demand.
2. Automatic Tidal: Executes water level adjustments based on predefined
settings without user intervention.
3. Manual: Allows users to directly control tidal settings for maintenance.
4. Faulty: Stops the related process (tidal or heating) as a safety measure.

<p align="center">
<img width="667" alt="image" src="https://github.com/user-attachments/assets/9ecb1b08-d7b8-4c7a-b3f0-7bc03c33c697">
</p>

The diagram illustrates the transitions between modes, which are governed by
three types of triggers:
1. Time-Out Based: The system automatically shifts modes after a certain time
without receiving commands or if a process takes too long.
2. User Command: The user manually initiates a mode change.
3. Process Control: The system's internal processes dictate the shift from one
mode to another, typically for calibration or error handling.
The transitions detailed in the state machine, with their respective triggers, are
designed to be flexible. The primary objective is to establish safety measures
through restrictions that govern the switch from one operating phase to another.

### Calibration Mode
This mode measures the total water displacement (Vinitial). It is a critical process that
allows for the assessment of water movement and ensures that all system
components are functioning correctly. During this process, time out values are
obtained for the later automatic monitoring:
• Rising time = Bottom-Middle + Middle-Top
• Falling time = Top-Middle + Middle-Bottom
If in any case a pumping operation reaches the timer of maximum duration (hardcoded),
the system will trigger a faulty system.
During rising tide, the flow meter can calculate the total water displacement.

<p align="center">
<img width="1021" alt="image" src="https://github.com/user-attachments/assets/fbb49d11-00e8-427f-9129-7f9ada2a6f0a">
</p>

__User Defined Tidal Height (Optional__
This development objective ensures that the water displacement during a rising tide
is adjustable. Consequently, the limit of the TOP state is no longer bound by the
level sensor but is instead determined by the adjusted rising time or by using a flow
meter. Due to the siphon effect, the BOTTOM level cannot be adjusted since it will
always drain to the lowest point. Implementing this feature for automatic tidal
requires more complex scheduling and will remain functional as long as the plant
level sensors stay in the same position. If the sensors are moved, a complete
calibration cycle will be necessary.

__ Automatic Tide Cycle__
This elementary process loops in an endless cycle of high and low tides in the plant
tank. Users can define the settings of the tide (High-Low Tide Duration & User-
Defined Tidal Height).
Doing so, the duration of a complete tide cycle is defined by:
• Total Tide Duration = Rising Time + Duration High Tide + Falling Time +
Duration Low Tide
In terms of state system and monitoring, the following truth table provides a
comprehensive overview:

| PTB | PTT | Level  | Direction | Next State    | Action/Comment                 | Issue |
|-----|-----|--------|-----------|---------------|--------------------------------|-------|
| 0   | 0   | Bottom | Rising    | MIDDLE        | Pump & Timer Control           | 0     |
|     |     |        | Falling   | WAIT→MIDDLE   | Tide done (Wait)               | 0     |
| 0   | 1   | DC     | DC        | DC            | Check Sensor Water             | 1     |
| 1   | 0   | Middle | Rising    | TOP           | Pump & Timer Control           | 0     |
|     |     |        | Falling   | BOTTOM        | Pump & Timer Control           | 0     |
| 1   | 1   | Top    | Rising    | WAIT→MIDDLE   | Tide done (Wait)               | 0     |
|     |     |        | Falling   | MIDDLE        | Pump & Timer Control           | 0     |
DC : Don’t care - ISSUE: 2 – no operation (faulty) / 1 – critical sensor situation (automatic) / 0 – no
restriction (automatic)


External perturbation occurs when a state change in the water level sensors (PTB,
PTT) during a no-pumping phase. This abnormal sensor behavior (indicating a fault)
can also result from an unexpected water loss or gain of the plant tank.
A faulty sensor should be detected during the rising phase by checking the flow
meter and timer’s benchmarks. Even when the sensors are not functioning (critical
sensor situation), if previously calibrated accurately, it can continue to operate using
the flow meter for the rising tide and a pre-set timer for the falling tide. To utilize the
siphon effect, a long low tide timer is employed. This issue should be resolved once
maintenance occurs, with a complete calibration cycle required to reset the system.
This situation should be addressed swiftly as the absence of overfill protection and
the potential for the pump to run dry could compromise system integrity. Therefore,
the user should be notified about the reduced safety mechanism.
Error management is further supported by timeout counters for different
operational phases. Transition durations are critically evaluated against two types
of limits:
• Variable values derived from calibration cycle mode.
• Hard-coded values serve as an additional layer of security (especially during
calibration and manual operation).
Should either set of limits be reached, the system is programmed to either transition
into a faulty state or operate with reduced functionality, alerting to a critical sensor
situation:

