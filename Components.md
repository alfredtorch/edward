Please if you need to shop for parts, it would be great that you use the supply links below. As they are affilated, you're supporting directly the development of Edward! Thank you!
The boards contains QWIIC connectors (3V3 Level). This allows to integrate many sensors from Adafruit or Sparkfun.

# Sensors

## Water Flow Meter 
<p align="center">
<img width="450" alt="image" src="https://github.com/user-attachments/assets/4e351981-9f5a-4c53-b4ae-eac67a5f55af">
</p>

Device| Integration | Notes | Board Compatbility | ToDo | Source |
|---|---|---|---|---|---|
Flow Meter|PCTN Counter| ESP32 internal Counter ESPHOME ✅ | GreenHouse, Fishtank, SSR8 : Level Shifter Missing | Design Translator PCB & Formula | [Aliexpress](https://s.click.aliexpress.com/e/_DBCUJ6n)
Flow Meter|DS1683 | Event Counter on I2C | Helios : Not yet test | Develop Component Software | [Aliexpress](https://s.click.aliexpress.com/e/_DBCUJ6n)

## Level and Limit Switch
<p align="center">
<img width="1040" alt="image" src="https://github.com/user-attachments/assets/840bd48d-2a28-47b8-aefa-60d3a1b0b904">
</p>

| Device | Notes | Board Compatbility | ToDo | Source |
|---|---|---|---|---|
|Limit Switch| Can be used for Chicken Coop Door, Floating switch | Greenhouse & FishTank : L1 - L2 | Fully Tested ✅| 
|Sonar| Measure Distance to Water Surface | GreenHouse : Not yet tested | |
|Optical Water | Can not be fully submerged (Tank mounted) | Greenhouse & Fishtank | Fully Tested ✅|
|Fuel Gauge | Solid Design - 5 stage 0 - 190Ohm | GreenHouse & Fishtank : Thermistor - SSR Rebel on Analog | Fully Tested ✅|

## Temperature
<p align="center">
<img width="655" alt="image" src="https://github.com/user-attachments/assets/8edb3dea-d23d-4769-af50-b4d19750e18d">
</p>

| Device | Notes | Board Compatbility | ToDo | Source |
|---|---|---|---|---|
|ds18b20| Digital One-Wire Temperature Sesnor | Greenhouse & FishTank & SSR | Fully Tested ✅ - Check Multiple Device|
|Thermistor| (10K)  | Greenhouse & FishTank & SSR8 &  | Not yet tested |

## Ambient & Air Quality
<p align="center">
<img width="157" alt="image" src="https://github.com/user-attachments/assets/bbfaf659-d034-4ed6-8a36-a47976b0b307">
</p>

| Device | Notes | Board Compatbility | ToDo | Source |
|---|---|---|---|---|
|BME680| Temperature, pressure, humidity, Quality sensor | Greenhouse & FishTank | Fully Tested ✅ -| [Aliexpress](https://s.click.aliexpress.com/e/_DBvNEJ5)

# Load Switching
## AC Switching
<p align="center">
<img width="463" alt="image" src="https://github.com/user-attachments/assets/1608a392-8e45-4024-8fd0-94fa0c324538">
</p>

| Device | Notes | Board Compatbility | ToDo | Source |
|---|---|---|---|---|
|Relay  | 5V 4 Channel  | Greenhouse with Relay - PCB  | Not yet Tested| [Aliexpress](https://s.click.aliexpress.com/e/_DFJCp8L)
|Solid State Relay | 8x 2Amp main SSR |Greenhouse with SSR - PCB  | Fully Tested ✅| [Aliexpress](https://s.click.aliexpress.com/e/_DkCJPYb)
|Dimmable Solid State Relay | 8x 2Amp main SSR | SSR Rebel with Zero Crossing Circuit  | Fully Tested ✅| Tindie Store soon

## DC Switching
<p align="center">
<img width="618" alt="image" src="https://github.com/user-attachments/assets/1e7d1dc8-28c3-47a2-bd6a-35c9a6d6608e">
</p>

| Device | Notes | Board Compatbility | ToDo | Source |
|---|---|---|---|---|
|Blued Mosfet  | COTS Module  5-36V at 15Amp  | Greenhouse with GSV Mosfet Rail PCB - PIO1-4 | Not yet Tested ✅  | [Aliexpress](https://s.click.aliexpress.com/e/_DFgjmCX)
|Black Mosfet | COTS Module different options : 30V-100V min 30Amp|  Greenhouse with SVG Mosfet Rail PCB PIO1-4 | Fully Tested ✅| [Aliexpress](https://s.click.aliexpress.com/e/_Dl0jIYB)
|On Board Switch | Power Smart Switch |  Fishtank PIO1-4 | Fully Tested ✅|

## Motors & Actuators
<p align="center">
<img width="1159" alt="image" src="https://github.com/user-attachments/assets/7b122d91-2c7b-4f5d-bfee-efbb2ecd6d6e">
</p>

| Device | Notes | Board Compatbility | ToDo | Source |
|---|---|---|---|---|
|Water Pump  | AC  | Greenhouse with SSR or Relay - SSR Rebel (dimming not recommanend | Tested ✅  | 
|Water Pump  | DC  | Greenhouse with Mosfet Rail PCB - Fishtank Load Switch  | Not yet Tested |
|28BYJ48  | Geared Stepper Motor  | Greenhouse with GSV Mosfet Rail PCB - PIO1-4 | Not yet Tested  |
|Servo | PWM Controller  | Greenhouse & Fistank : Servo 1 2  | Not yet Tested  |
|Valve | AC DC  | Greenhouse with Load Rail PCB - PIO1-4 | Not yet Tested |
|Fan  | DC  | Greenhouse & Fish House PCTN - Helios EMC2102 Fan | Not yet Tested |


## Light
<p align="center">
<img width="923" alt="image" src="https://github.com/user-attachments/assets/d7b7b36d-e4ce-476a-b356-95fc76a2ec44">
</p>

| Device | Notes | Board Compatbility | ToDo | Source 
|---|---|---|---|---|
| Aquarium 8 Channels Module | COTS Module | Helios | Fully  Tested ✅|| [Aliexpress](https://s.click.aliexpress.com/e/_DFJCp8L)
| DC Led Driver Module | COTS Module )  | Helios : 1 ex. PWM Green House & Fishtank : Servo 1 - 2 | Fully  Tested ✅|| [Aliexpress](https://s.click.aliexpress.com/e/_DD5UYUn)
| LED 230AC | COTS Module (30-50 Watt) Different Wavelengts |  GreenHouse with SSR (On Off) - SSR Rebel (dimming)  | Fully Tested ✅| [Aliexpress](https://s.click.aliexpress.com/e/_DkCJPYb)

### Aquarium Module 8 Channel
<p align="center">
 <img width="527" alt="image" src="https://github.com/user-attachments/assets/4f1ba150-cdbf-4a0e-97e0-a1164266668d">
</p>
DC 3W 5-35V Led Driver Step Down : Exist for 350mA and 700mA.

* [Datasheet](https://www.led-stuebchen.de/download/PT4115E.pdf)
* [Aliexpress 1-3Watt Driver ](https://s.click.aliexpress.com/e/_DkGRYXz)
* [Aliexpress LED Module](https://de.aliexpress.com/item/1005002624762658.html?spm=a2g0o.productlist.0.0.7b371c3dJNj5MA&mp=1&gatewayAdapt=glo2deu)

| Channel   | Color    | Wavelength (nm) | Current (mA) | Voltage (V) | Power (W) | Quantity |
|-----------|----------|-----------------|--------------|-------------|-----------|----------|
| Red       | Red      | 650-670         | 700          | 4.0-4.4     | 2.94      | 2        |
| Green     | Green    | 520-530         | 700          | 6.0-6.4     | 4.34      | 2        |
| Deep Blue | Deep Blue| 450-470         | 700          | 12-13       | 8.75      | 4        |
| White     | White    | 6000-8000K      | 700          | 12-13       | 8.75      | 4        |
| Yellow    | Yellow   | 585-595         | 700          | 2.0-2.2     | 1.47      | 1        |
| Violet    | Violet   | 410-430         | 700          | 12-13       | 8.75      | 3        |
| UV        | UV       | 390-410         | 700          | 6.4-6.6     | 4.55      | 2        |

__Theoretical Power Figures__
**Total Power Consumption:** 48.3W  
**Required Voltage for LED Driver:** 15V (safe margin)  
**Typical Step-Down LED Driver Input Voltage:** 24V
**Need to double check LED numbers and specifications**




