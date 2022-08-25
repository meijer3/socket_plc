# Pling chip: a pcb-controller for PLC

<img src="readme_resources\pling_relays_3d.png"  />
This project contains a PCB (concept) that is designed for WAGO PLC200, but should work with all DO/DI. Limiting wired connection as much as possible.

> Developers use case:
>
> I have a sit-stand desk with computer. With two buttons/relay can I turn on or off the laptop and/or other electrics like lights. The goal is to save energy and make my workstation smart.
>
> An second version would be nice to control blinds, and add two buttons to control the blinds locally

.

# Concept

This project has two main concepts which should not be confused.

## 1. Wired PLC communication:

Should **always** work, even without internet/mqtt/home-assistant. PLC is reliable enough.

### Option A

- 2 Relay (24v - 230v)
- 2 Push buttons (24v) optional: with led linked to relay.

### Option B (After first prototype)

- Sun-screens/blinds (24v - 230v)
- Up an Down buttons (24v)

## 2. Wired ESP communication:

Non-important (but nice to have) data

- Wired communication `Rx/Tx` back to a central `single-board-computer` linked to `MQTT`.
- `3.3v`/`5v`/`GRN` output for `ESP`
- Possible extra sensors to communicate back
  - Power consumption
  - Temperature
  - Extra DO/IO
    - more lamps
  - Analog input/output
    - Desk

# Design of ethernet cable.

|  #  |             Cable             |                          Color&nbsp; &nbsp; &nbsp;                          |      Funtion      |
| :-: | :---------------------------: | :-------------------------------------------------------------------------: | :---------------: |
|  1  | WhiteOrange&nbsp;&nbsp;&nbsp; | <img src="readme_resources\rj45\WhiteOrange.jpg" style="max-width:60px;" /> | Return of Pulse 1 |
|  2  |            Orange             |   <img src="readme_resources\rj45\Orange.jpg" style="max-width:60px;" />    | Return of Pulse 2 |
|  3  |          WhiteGreen           | <img src="readme_resources\rj45\WhiteGreen.jpg" style="max-width:60px;" />  |        GND        |
|  4  |             Blue              |    <img src="readme_resources\rj45\Blue.jpg" style="max-width:60px;" />     |        RX         |
|  5  |           WhiteBlue           |  <img src="readme_resources\rj45\WhiteBlue.jpg" style="max-width:60px;" />  |        TX         |
|  6  |             Green             |    <img src="readme_resources\rj45\Green.jpg" style="max-width:60px;" />    |        24v        |
|  7  |          WhiteBrown           | <img src="readme_resources\rj45\WhiteBrown.jpg" style="max-width:60px;" />  |  Feed of relay 1  |
|  8  |             Brown             |    <img src="readme_resources\rj45\brown.jpg" style="max-width:60px;" />    |  Feed of relay 2  |

# Design of PCB

<img src="readme_resources\pling_relays_schema.png"  />

My [easyEDA](https://easyeda.com/editor#id=6322c5ac72684001988da50a786b0ca6|d3c61f0f50fa44159afa5726d664ce04) design. I am not a great PCB builder. So please help me out.

### More info

[Buck converter 24 - 3.3](https://electronicsworkshops.com/2021/01/02/design-of-24v-to-3-3v-buck-converter/)

[other buck exmple](https://www.pcbway.com/project/shareproject/3_3V_5A_DC_DC_Converter.html)
