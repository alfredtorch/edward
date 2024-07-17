<img width="1044" alt="image" src="https://github.com/alfredtorch/edward/assets/38537119/efd46c8c-8d4a-45d7-ad58-6c7031de8b7f">
Edward is an innovative solution that synergizes citizen science with urban farming, utilizing an advanced aquaponic system to address environmental challenges. Edward aims to produce sustainable food sources while fostering community involvement and contributing to a healthier, more sustainable urban environment.

Envisioned as an expansive urban farming laboratory, Edward initially focuses on aquaponics. This highly efficient farming method is capable of producing local food with minimal resource impact and effort. By transforming existing water bodies, such as ponds or basins, into productive food sources, Edward epitomizes the principles of the circular economy.

Key Features
- Smart Garden Community: Build your self-sufficient technology platform and transform public spaces into urban farming areas.
- Citizen Science: Share information and engage in community-driven research.
- Open Source: Driven by the community, promoting collaboration and innovation.
- Modular Design: Based on the principles of the circular economy, allowing adaptability and scalability.
<p align="center">
<img width="600" alt="image" src="https://github.com/alfredtorch/edward/assets/38537119/b09d52ce-bccf-47e4-86c5-7ff1bcfb4936">
</p>

# Growing Lab & Sharing Knowledge
Edward fosters continuous improvement through community involvement at multiple levels. Individuals manage local stations, benefit from fresh food, and participate in testing new biological scenarios. This approach enriches community knowledge and enhances the numerical model.

<p align="center">
<img width="800" alt="image" align="center" src="https://github.com/alfredtorch/edward/assets/38537119/cf328e57-753d-48ca-9412-3c478e19aede">
</p>

The Sustainable Food Cycle and Optimization Biological Cycle are central to Edward's innovative approach. The Sustainable Food Cycle focuses on creating a cradle-to-cradle system where organic waste is transformed into bio converters and natural bio cycles, producing organic food for fish and yielding fresh vegetables. This cycle epitomizes resource efficiency and sustainability. Meanwhile, the Optimization Biological Cycle leverages citizen science and advanced technologies like machine learning and autonomous control to refine and enhance farming practices. Through community-driven research, scenario experimentation, and gamification, this cycle ensures continuous improvement and optimization of the entire system.

<p align="center">
<img width="1080" alt="image" src="https://github.com/alfredtorch/edward/assets/38537119/75d94cd6-c0b5-40ef-9fd4-1325d9848cdc">
</p>

## Sharing Knowledge
For individuals, Edward offers a novel way to connect with nature and their community. Members assume shared responsibility for their plants and fish, gaining knowledge and forming new connections, both digitally and in person. This hands-on experience not only yields healthy food but also underlines a Return on Research (RoR) approach, valuing the knowledge gained from community-led research and innovation.

Key Features
- Citizen-Operated Stations: Gather observations for new biological scenarios like light conditions or tidal cycles.
- Mobile App Support: Easy sharing of observations with scientists, encouraging dynamic information exchange.
- Participative and Gamified Approach: Encourages dialogue, sharing through text and images, and collective data contribution.
- AI-Driven Insights: Data from multiple stations feed into AI models for valuable insights into small-scale and industrial agricultural practices, such as pisciculture.

## Research Project 1 : Water Cooled LEDs
<img width="1120" alt="image" src="https://github.com/alfredtorch/edward/assets/38537119/308338e6-abe0-4e30-807d-cb491b769f31">

Improve the maintenance cost and efficiency with water cooled LED. The study is focusing in efficient thermal management of the growlight. On one hand an optimal cooling will provide long term stable light caracteristics and raise lifespan. On the hand, the possible to heat the fish tank from local waste heat.
### Phase
1. Design Possibilities (Heat Sink, LED Holder, ...)
2. Check Safety Concerns (electrocution, fire, light amount)
3. Regulate Water pump and light intensity (based on state machine and scheduling)
4. Measure (Light quality (Energy and Wavelengths, Consumption) over time

# Product Development
<img width="1406" alt="image" src="https://github.com/alfredtorch/edward/assets/38537119/004e3b65-0283-4ce5-85df-1a174a9744d0">
** [Software Page](SoftwareSpecificationSheetM2.md)
The current prototype system is powered by Home Assistant with ESPHome running on a local Raspberry Pi1. The main challenges faced by the current system include:
• not a standalone system (Raspberrypi + Station Controller)
• no option for easy remote monitoring of the system (NAT, DNS)
• missing control options (regular self-calibration, failsafe mode)

More details about the electronics designed circuits, uaed materials etc.. are shared on hardware.md

<p align="center>
  ><img width="457" alt="image" src="https://github.com/alfredtorch/edward/assets/38537119/16de9607-761a-44c0-bd4a-c8bdb59ee4df">
</p>

## Development Project 1 : Switch from HA Setup to independant Station MCU with remote connectivity

You can find the current 
## Files & Folders

## [Hardware Page](Hardware.md)
## [Hardware PCB Folder](/Hardware/)
## [Software Page](/Software/)
## [Software Devlopment Specification Sheet](SoftwareSpecificationSheetM2.md)


