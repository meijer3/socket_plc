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

|  #  |             Cable             |                                                                 Color&nbsp; &nbsp; &nbsp;                                                                  |      Funtion      |
| :-: | :---------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------: | :---------------: |
|  1  | WhiteOrange&nbsp;&nbsp;&nbsp; | <img src="readme_resources\rj45.jpg"  style="position: absolute; min-height:100px; clip: rect(5px,192px,15px,0px); transform:translate(-40px, -10px);" />  | Return of Pulse 1 |
|  2  |            Orange             | <img src="readme_resources\rj45.jpg"  style="position: absolute; min-height:100px; clip: rect(15px,192px,25px,0px); transform:translate(-40px, -20px);" /> | Return of Pulse 2 |
|  3  |          WhiteGreen           | <img src="readme_resources\rj45.jpg"  style="position: absolute; min-height:100px; clip: rect(26px,192px,36px,0px); transform:translate(-40px, -30px);" /> |        GND        |
|  4  |             Blue              | <img src="readme_resources\rj45.jpg"  style="position: absolute; min-height:100px; clip: rect(38px,192px,48px,0px); transform:translate(-40px, -40px);" /> |        RX         |
|  5  |           WhiteBlue           | <img src="readme_resources\rj45.jpg"  style="position: absolute; min-height:100px; clip: rect(48px,192px,58px,0px); transform:translate(-40px, -50px);" /> |        TX         |
|  6  |             Green             | <img src="readme_resources\rj45.jpg"  style="position: absolute; min-height:100px; clip: rect(59px,192px,69px,0px); transform:translate(-40px, -62px);" /> |        24v        |
|  7  |          WhiteBrown           | <img src="readme_resources\rj45.jpg"  style="position: absolute; min-height:100px; clip: rect(70px,192px,80px,0px); transform:translate(-40px, -74px);" /> |  Feed of relay 1  |
|  8  |             Brown             | <img src="readme_resources\rj45.jpg"  style="position: absolute; min-height:100px; clip: rect(80px,192px,90px,0px); transform:translate(-40px, -84px);" /> |  Feed of relay 2  |

# Design of PCB

<img src="readme_resources\pling_relays_schema.png"  />

My [easyEDA](https://easyeda.com/editor#id=6322c5ac72684001988da50a786b0ca6|d3c61f0f50fa44159afa5726d664ce04) design. I am not a great PCB builder. So please help me out.

### More info

[Buck converter 24 - 3.3](https://electronicsworkshops.com/2021/01/02/design-of-24v-to-3-3v-buck-converter/)

[other buck exmple](https://www.pcbway.com/project/shareproject/3_3V_5A_DC_DC_Converter.html)
