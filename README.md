UT22 Rear Controller v.3.1
By: Benjamin Liang, Senior Electrical Member, University of Toronto Formula Racing Team
In this article, we will explore v.3.1 of the rear controller for UT22, the car we’re taking to competition this season. Each year, the University of Toronto Formula Racing Team (UTFR) designs and builds a new car to compete in international Formula SAE events. As such, the team must ensure all elements of the vehicle comply entirely with Formula SAE regulations, the rear controller is no exception. This PCB controls the car’s power distribution, data acquisition, CAN Bus communication, low voltage battery management system, high voltage integration, accelerator pedal position sensor (APPS) signal transmission, cooling system, traction control, and numerous safety features.

![image](https://user-images.githubusercontent.com/82067858/163696802-64a019b0-70ba-4c65-9f0d-db92673a1dd2.png)
 
Due to issues supplying Atmega2560s as a result of the global silicon shortage and delays to our timeline due to COVID-19, we decided to implement a modular design for this revision of the rear controller. This includes a shield for an Arduino Mega, Arduino Micro, three switching regulator modules, three CAN Bus modules, a DAC module used to transmit the APPS signal to the inverter, a gyroscope module, and an accelerometer module. The CAN Bus modules in particular consist of a CAN controller and transceiver used for communication with other CAN Bus nodes within the car’s data acquisition architecture.

 
This PCB is a culmination of an unprecedented year-long design cycle due to all of the challenges we’ve faced and our switch to EV. This amazing learning process and period of PCB development within our team was only possible thanks to the help of JLCPCB (https://jlcpcb.com/RAT). Founded in 2006, JLCPCB (https://jlcpcb.com/RAT) is a leading global PCB manufacturer with over 16 years of experience providing the best customer experience through the rapid production of highly reliable and cost-effective PCBs.
 
Schematic Design
Specifically, the controller design revolves around an Arduino Mega as the primary MCU connected to an Arduino Micro as the secondary MCU. The Arduino Mega is responsible for controlling the car’s power distribution system, battery management system, data acquisition, CAN Bus communication, high voltage integration, dash lights, cooling system and shutdown circuit trip detection. The Arduino Micro is dedicated to processing drive critical signals such as brake and accelerator pedal positions, as well as wheel speed data for traction control.
 
The power distribution architecture within the board consists of power coming directly from the car’s 4S2P LiPo battery and power regulated using the switching regulators at 12V, 8V and 5V. The unregulated power distribution as well as the 12V, 8V, and 5V regulators are shown below.
 
All power nets are protected by thermal fuses and the high current net including inverter power, radiator fan power and cooling pump power are controlled by relays actuated by the Arduino Mega. The thermal fuse holders are shown in the schematics above and the relay circuits are shown below.
 
PCB Layout
Altium Designer, a PCB and electronic design application was used to design the rear controller. The controller circuits were created by placing the required components on schematics and wiring them together in the required configuration. Each component is assigned a footprint that represents the physical dimensions of the component. Once the designer is satisfied with the PCB layout, the footprints are then routed in the exact manner shown in the schematics. The project can then be saved and the Gerber files exported.
 
JLCPCB Order
The main controller was ordered from JLCPCB (https://jlcpcb.com/RAT) for quick, reliable, and cost-effective manufacturing. This ordering process is extremely simple and consists of the following four quick steps:
1.	Export Gerber files from Altium
2.	Click on the quote now button on the JLCPCB (https://jlcpcb.com/RAT) website
3.	Upload the Gerber files and double-check the PCB in the Gerber viewer then
4.	Click save to cart, select your shipping and pay.
JLCPCB (https://jlcpcb.com/RAT) automatically detects all the PCB specifications, and fills out the order form for you.
 
Furthermore, JLCPCB (https://jlcpcb.com/RAT) also provides an SMT service which fulfills the money and time saving needs of customers at only an $8.00 setup fee ($0.0017 per joint). It is a one stop online platform where you can also track the progress of your PCBA manufacturing process (completed within a day) in real time. Through the platform you can conveniently source thousands of components from JLCPCB (https://jlcpcb.com/RAT) and its reliable component partners like Digikey and Mouser. The quality and reliability are always superb with professionally trained engineers, inspection methods such as X-ray and automated optical inspection, automated component placement and various soldering techniques (reflow, wave and manual).
