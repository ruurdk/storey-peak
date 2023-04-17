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

| Silkscreen | Identifier | Mnfg. | Function | Doc link | I2C address |
| -- | ---- | --- | --- | --- | --- |
| U1 | Stratix V GS | Altera/Intel | FPGA | | N/A |
| U2 | 25Q256A 83C40 | Micron | 256-Mbit Serial NOR Flash Memory | | N/A |
| U3 | FT232H | FTDI | Single channel HiSpeed USB to Multipurpose UART/FIFO | | N/A |
| U4/OSC3 | IDT8N4Q001 | Renesas | Quad-Frequency Programmable XO | | 0x6eh |
| U5 | T411 | Texas Instruments | Remote and local temperature sensor | | 0x4Ch |
| U9 | PI6CEQ200 | Pericom | PCIe Gen2/Gen3 buffer | | 0x6ah |
| U16 | 4128BWP | ST | 128-kbit serial EEPROM | | |
| U74  | P617A | NXT | Level translating Fm+ I2C-bus repeater | | N/A |
| U46,48,50,52,54,56,58,60,64 | HSTC4G83BFR | SKhynix | 4-Gbit 1.35V DDR3L SDRAM | | N/A |

Power parts:
| Silkscreen | Identifier | Mnfg. | Function | Doc link |
| --- | --- | --- | --- | --- |
| PU 1 | 7100 FXPF 1548 | ?? | ?? | |
| PU3, 5, 7 | 2120 F551KS 1551 | ?? | ?? | |
| PU8 | 3105 XXJS 1547 | ?? | ?? | |
| PU10, PU15? | EN2342QI | Altera/Enpirion | ?? | |
| PU12 | s1010 | Altera/Enpirion | 12V Hot-swap Power distribution controller | |
| PU13 | Y1602A | ?? | ?? | |
| PU17 | ?? | ?? | |


Oscillators:
| Silkscreen | Identifier | Frequency |
| --- | --- | --- |
| OSC1 | | |
| OSC3 | | |
| OSC4/U4 | IDT8N4Q001 | |
| Y1 (near FT232H) | | |


Headers and connectors:
| Silkscreen | Function | Link |
| --- | --- | --- |
| J5 | JTAG | |
| J3 | USB? | |
| JP1 | ??? | |
| CN1 | USB | |
| XCVR1 + U63 | QSFP 40Gbit | |
| XCVR2 + U64 | QSFP 40Gbit | |


Unknown:
| Silkscreen | Identifier | 
| --- | --- |
|  | AUPPK U610 | 
| U38 (back) | |
| U73 |  |
| U75 | L57 |
| U78 |  | 

## Included repos

- 

## Pins/connections
