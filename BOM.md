# BOM

Part number for this board: 
- X930613-001 (Microsoft OEM p/n)
- 861309-001 Rev B (HP p/n)

The main ICs on the board:

| Silkscreen | Identifier | Mnfg. | Function | I2C address |
| -- | ---- | --- | --- | --- |
| U1 | Stratix V GS | Altera/Intel | FPGA | N/A |
| U2 | 25Q256A 83C40 | Micron | 256-Mbit Serial NOR Flash Memory | N/A |
| U3 | FT232H | FTDI | Single channel HiSpeed USB to Multipurpose UART/FIFO | N/A |
| U4/OSC3 | IDT8N4Q001 | Renesas | Quad-Frequency Programmable XO | 0x6eh |
| U5 | T411 | Texas Instruments | Remote and local temperature sensor | 0x4Ch |
| U9 | PI6CEQ200 | Pericom | PCIe Gen2/Gen3 buffer | 0x6ah |
| U16 | 4128BWP | ST | 128-kbit serial EEPROM | 0x51h |
| U46,48,50,52,54,56,58,60,64 | HSTC4G83BFR | SKhynix | 4-Gbit 1.35V DDR3L SDRAM | N/A |
| U74  | P617A | NXT | Level translating Fm+ I2C-bus repeater | no bus address |
| U75 | L57 | TI | TS3USB221 USB 2.0 1:2 mux/demux switch with single enable | N/A |
| U77,78 | WR1 61 | ?? | ESD protection diode | N/A |

Unknown I2C 0x41h address responder.

Oscillators:

| Silkscreen | Identifier | Mnfg. | Frequency |
| --- | --- | --- | --- |
| OSC2 | DCpA3 | TXC | 125Mhz |
| OSC3/U4 | IDT8N4Q001 | Renesas | programmable (644.53125 MHz default) | 
| Y1 | 12.000 623L | ?? | 12Mhz? | 

Headers, connectors and jumpers:

| Silkscreen | Function | Extra info |
| --- | --- | --- |
| J3 | USB (internal) | |
| J5 | JTAG | |
| J4 | PCIe x16 (2x x8 bifurcated to hard IPs) | |
| JP1 | jumpers - but for what? | |
| CN1 | USB (external) | |
| XCVR1 + U63 | QSFP SFF-8636 40Gbit transceiver | I2C 0x50h when inserted (seperate bus) |
| XCVR2 + U64 | QSFP SFF-8636 40Gbit transceiver | I2C 0x50h when inserted (seperate bus) |

Power parts:

| Silkscreen | Identifier | Mnfg. | Function |
| --- | --- | --- | --- |
| PU 1 | 7100 | Intel | EC7100VQI PWM DC/DC Controller with VS inputs for FPGA power regulator |
| PU3, 5, 7 | 2120 | Intel | ER2120QI 2A synchronous buck regulator |
| PU8 | 3105 | Intel | ER2105DI 500mA wide V_in Synchronous Buck regulator |
| PU10,16 | EN2342QI | Intel | EN2342QI 4A PowerSOC DC-DC switching converter |
| PU12 | s1010 | Intel | ES1010SI 12V Hot-swap Power distribution controller |
| PU13 | Y1602A | Intel | EY1602 40V 50mA linear regulator |

Unknown:

| Silkscreen | Identifier | 
| --- | --- |
| ?? | AUPK U610 (near NOR flash) 16 pin| 
| U38 (back) | |
| U65 | F DG06A |
| U73 | MX 6 (near PCIe) 6 pin |
| PU17 | 70H | ?? | |