# storey-peak
Collected resources and getting started with Azure PCIe FPGA device

## Introduction

Getting started with production grade high-end FPGA devices is usually either extremely expensive (with official dev kits) or daunting (using refurbished hardware). This makes it prohibitive to start as a hobbyist.

There is a body of knowledge around the MSFT Azure Storey Peak boards which can be bought online for $80.

In this repo, I collect the different sources available online and add some of my own code that makes this all work on Windows.

There is a blog to support this repo on getting started quickly [here](todo).

## Online sources

- the central piece that got me started was the blog series by (Jan Marjanovic)[https://j-marjanovic.io/stratix-v-accelerator-card-from-ebay.html], starting around the OCS form factor 'Pikes peak' which is essentially the same - just not with SAMTEC but PCIe connector.
- PDF describing MSFT's [journey with FPGAs](https://indico.fnal.gov/event/22303/contributions/246438/attachments/157852/206736/Catapult_Putnam_Snowmass_2022_FPGA_Cloud__for_HPC.pdf). The board here is part of Catapult v2 (yes they go up to v3 and (further)[https://github.com/tow3rs/catapult-v3-smartnic-re/issues/2])
- overview by (Rombik)[http://virtlab.occamlab.com/home/zapisnik/microsoft-catapult-v2]

## Architecture and features

## BOM

The main ICs on the board:

| Silkscreen | Identifier | Mnfg. | Function | I2C address |
| -- | ---- | --- | --- | --- | --- |
| U1 | Stratix V GS | Altera/Intel | FPGA | N/A |
| U2 | 25Q256A 83C40 | Micron | 256-Mbit Serial NOR Flash Memory | N/A |
| U3 | FT232H | FTDI | Single channel HiSpeed USB to Multipurpose UART/FIFO | N/A |
| U4/OSC3 | IDT8N4Q001 | Renesas | Quad-Frequency Programmable XO | 0x6eh |
| U5 | T411 | Texas Instruments | Remote and local temperature sensor | 0x4Ch |
| U9 | PI6CEQ200 | Pericom | PCIe Gen2/Gen3 buffer | 0x6ah |
| U16 | 4128BWP | ST | 128-kbit serial EEPROM | 0x51h |
| U46,48,50,52,54,56,58,60,64 | HSTC4G83BFR | SKhynix | 4-Gbit 1.35V DDR3L SDRAM | N/A |
| U74  | P617A | NXT | Level translating Fm+ I2C-bus repeater | no bus address |


Power parts:
| Silkscreen | Identifier | Mnfg. | Function |
| --- | --- | --- | --- | --- |
| PU 1 | 7100 | Intel | EC7100VQI PWM DC/DC Controller with VS inputs for FPGA power regulator |
| PU3, 5, 7 | 2120 F551KS 1551 | Intel | ER2120QI 2A synchronous buck regulator |
| PU8 | 3105 | Intel | ER2105DI 500mA wide V_in Synchronous Buck regulator |
| PU10,16 | EN2342QI | Intel | EN2342QI 4A PowerSOC DC-DC switching converter |
| PU12 | s1010 | Intel | ES1010SI 12V Hot-swap Power distribution controller |
| PU13 | Y1602A | Intel | EY1602 40V 50mA linear regulator |
| PU17 | 70H | ?? |


Oscillators:
| Silkscreen | Identifier | Mnfg. | Frequency |
| --- | --- | --- |
| OSC2 | DCpA3 | TXC | 125Mhz |
| OSC3/U4 | IDT8N4Q001 | Renesas | programmable (644.53125 MHz default) | 
| Y1 (near FT232H) | 12.000 623L | ?? | 12Mhz? | 


Headers, connectors and jumpers:
| Silkscreen | Function | Link |
| --- | --- | --- |
| J3 | USB? | |
| J5 | JTAG | |
| J4 | PCIe x16 (2x x8) | |
| JP1 | jumpers - but for what? | |
| CN1 | USB | |
| XCVR1 + U63 | QSFP 40Gbit | |
| XCVR2 + U64 | QSFP 40Gbit | |



Unknown:
| Silkscreen | Identifier | 
| --- | --- |
|  | AUPPK U610 | 
| U38 (back) | |
| U65 | F DG06A |
| U73 | MX 6 (near PCIe) |
| U75 | L57 (near USB) |
| U77 | WR1 61 |
| U78 | WR1 61 | 
| Q12 | F ACO6AS FDMS 0310AS |

Unknown I2C 0x41h address responder.

## Included repos

- 

## Pins/connections
