# Sensors

## Water Flow Meter 
<p align="center">
<img width="450" alt="image" src="https://github.com/user-attachments/assets/4e351981-9f5a-4c53-b4ae-eac67a5f55af">
</p>


| Strategy | Notes | Board Compatbility | ToDo |
|---|---|---|---|
|PCTN Counter| ESP32 internal Counter ESPHOME ✅ | GreenHouse, Fishtank, SSR8 : Level Shifter Missing | Design Translator PCB & Formula 
|DS1683 | Event Counter on I2C | Helios : Not yet test | Develop Component Software

## Level and Limit Switch
<p align="center">
<img width="1040" alt="image" src="https://github.com/user-attachments/assets/840bd48d-2a28-47b8-aefa-60d3a1b0b904">
</p>

| Strategy | Notes | Board Compatbility | ToDo |
|---|---|---|---|
|Limit Switch| Can be used for Chicken Coop Door, Floating switch | Greenhouse & FishTank : L1 - L2 | Fully Tested ✅|
|Sonar| Measure Distance to Water Surface   | GreenHouse : Not yet tested | |
|Optical Water | Can not be fully submerged (Tank fixation) | Greenhouse & Fishtank | Fully Tested ✅|
|Fuel Gauge | Solid Design - 5 stage 0 - 190Ohm | GreenHouse & Fishtank : Thermistor - SSR8 on Analog | Fully Tested ✅|

## Temperature
<p align="center">
<img width="655" alt="image" src="https://github.com/user-attachments/assets/8edb3dea-d23d-4769-af50-b4d19750e18d">
</p>

| Strategy | Notes | Board Compatbility | ToDo |
|---|---|---|---|
|ds18b20| Digital One-Wire Temperature Sesnor | Greenhouse & FishTank & SSR | Fully Tested ✅ - Check Multiple Device|
|Thermistor| (10K)  | Greenhouse & FishTank & SSR8 &  | Not yet tested |

## Airquality
| Strategy | Notes | Board Compatbility | ToDo |
|---|---|---|---|
|ds18b20| Digital One-Wire Temperature Sesnor | Greenhouse & FishTank & SSR | Fully Tested ✅ - Check Multiple Device|

# Load Switching
## AC Switching
<p align="center">
<img width="493" alt="image" src="https://github.com/user-attachments/assets/1608a392-8e45-4024-8fd0-94fa0c324538">
</p>

| Strategy | Notes | Board Compatbility | ToDo |
|---|---|---|---|
|Relay  | 5V 4 Channel  | Greenhouse with PCB  | Not yet Tested|
|Solid State Relay | Greenhouse with SSR - PCB  | Fully Tested ✅|

## DC Switching
<p align="center">
<img width="718" alt="image" src="https://github.com/user-attachments/assets/1e7d1dc8-28c3-47a2-bd6a-35c9a6d6608e">
</p>

| Strategy | Notes | Board Compatbility | ToDo | Source |
|---|---|---|---|---|
|Relay  | 5V 4 Channel  | Greenhouse with PCB  | Not yet Tested | http |
|Solid State Relay | Greenhouse with SSR - PCB  | Fully Tested ✅ | http |

## Waterpumps

## Servo

## Stepper

28BYJ

## Light

### Led Driver Module
DC 3W 5-35V Led Driver Step Down : Exist for 350mA and 700mA. 
<img width="406" alt="image" src="https://github.com/user-attachments/assets/0aacc0df-162c-4c88-94aa-e2633154ddb7">
https://www.led-stuebchen.de/download/PT4115E.pdf

### LED Module Channel Specifications (Optional)

<p align="center">
<img width="400" alt="image" src="https://github.com/user-attachments/assets/e23efa59-5471-4533-8dc1-82ef9a806d20">
</p>


| Channel   | Color    | Wavelength (nm) | Current (mA) | Voltage (V) | Power (W) | Quantity |
|-----------|----------|-----------------|--------------|-------------|-----------|----------|
| Red       | Red      | 650-670         | 700          | 4.0-4.4     | 2.94      | 2        |
| Green     | Green    | 520-530         | 700          | 6.0-6.4     | 4.34      | 2        |
| Deep Blue | Deep Blue| 450-470         | 700          | 12-13       | 8.75      | 4        |
| Blue      | Blue     | 450-470         | 700          | 12-13       | 8.75      | 4        |
| White     | White    | 6000-8000K      | 700          | 12-13       | 8.75      | 4        |
| Yellow    | Yellow   | 585-595         | 700          | 2.0-2.2     | 1.47      | 1        |
| Violet    | Violet   | 410-430         | 700          | 12-13       | 8.75      | 3        |
| UV        | UV       | 390-410         | 700          | 6.4-6.6     | 4.55      | 2        |

**Total Power Consumption:** 48.3W  
**Required Voltage for LED Driver:** 15V (safe margin)  
**Typical Step-Down LED Driver Input Voltage:** 24V

https://de.aliexpress.com/item/1005002624762658.html?spm=a2g0o.detail.0.0.1066oEUzoEUzVt&mp=1&gatewayAdapt=glo2deu

### External LED Driver Module
 
### Addressable LED Strip

