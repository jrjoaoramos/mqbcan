![Example of CAN messages dump.](https://github.com/jrjoaoramos/mqbcan/blob/master/imgs/readme.png?raw=true)

# MQB Platform CAN
This projects aims to identify and analyse the CAN buses that lie in the Volkswagen Group MQB Platform based cars.
## Introduction
There are plenty cars based on this famous platform developed by VAG. They share the same base that allows developers and make them pleasant to research into them and make spectacular things. As such, this repo shares some of the findings that the community find.

## Target cars
The examples found here can be applied, theoretically, to any MQB car. Although, considering that we don't have access to all of them, currently they are tested in:

- <b>Seat Leon 5F</b>

They can also be applied, of course, to:
- <b>Audi A3 8V</b>
- <b>Volkswagen Golf MK7</b>

## CAN-BUS architecture
The first interface available for diagnosis and development is the OBD connector. It is directly connected to the "main" module of the car that is the CAN Gateway (with hex address 19). That module filters all the data that goes inside the car and just replies for the commands that are asked to it. Thus, it is harder to get access to all the functions of the car. Also, there are many CAN buses available: for engine communication, for confort communication and for infotainment communication. There are even other buses for communication between individual components that aren't broadcasted to the main CAN buses. This way, after analysing the OBD communication there is a need to tap into the specific buses, for example, in the radio Quadlock connector located in the back side.\
The communication bitrate is <b>500kB/s</b>.

## Goals
The main goals for this project is to share and create a community for the development and analysis of these cars' CAN-BUS architecture. As such, there are created documents to explain how to obtain the desired feature and scripts to perform those features automatically or in a semi-automatic fashion.
The final goal for this project is to develop an application in which we can use a smartphone/tabled and a standard Bluetooth CAN adapter to perform things like: open/close windows, turn on/off lights, lock/unlock the car, change radio settings, change A/C settings and so on :)

## Current state
Currently there are being taken dumps from existing applications for common OBD adapter such as VAS, VCDS and VAG CAN PRO. Based on them, the CAN messages are analysed and then replicated. With those messages, there is the possibility to aggregate all the functions in our custom OBD adapters and implement new different features.

## How to start
In order to take dumps of CAN buses, there may be required some special devices. Some OBD-compliant softwares already allow us to record the messages that flow from the device to the car, but others are very closed and restrict. As such, there may be needed on of the following adapters or similar.

For those adapters, I recommend the usage of these amazing utilities:\https://github.com/linux-can/can-utils (Docs: https://sgframework.readthedocs.io/en/latest/cantutorial.html).\
Assuming that you configure your adapter as "can0", you can access commands like:
- <b>candump can0</b> - watch in the standard output the CAN messages that are flowing
- <b>candump -l can0</b> - save all the CAN messages to a text file
- <b>cansniffer can0</b> - watch in the standard output the CAN messages that are changing some bytes and decode them in real-time
- <b>canplayer -I</b> <filename> -> send the CAN messages from the specified file to the CAN adapter
- <b>cansend can0</b> <CAN message> -> send the specified CAN message to the CAN adapter

### CAN-BUS adapters
- <b>CAN-BUS Shield V2.0</b>\
(http://wiki.seeedstudio.com/CAN-BUS_Shield_V2.0)
![alt text](https://github.com/SeeedDocument/CAN-BUS-Shield-V2.0/raw/master/img/CAN_BUS_Shield_V2.jpg)

- <b>USB CAN Analyzer</b>\
(https://www.seeedstudio.com/USB-CAN-Analyzer-p-2888.html)
![alt text](https://statics3.seeedstudio.com/seeed/file/2017-06/bazaar487719_1.jpg)

- <b>Serial CAN-BUS Module based on MCP2551 and MCP2515</b>\
(https://www.seeedstudio.com/Serial-CANBUS-Module-based-on-MCP2551-and-MCP2515-p-2924.html)
![alt text](https://statics3.seeedstudio.com/seeed/file/2018-08/bazaar891352_img_2945a.JPG)

## Analysed procedures
The analysis can be done via many different ways. For example, it can be via the OBD connector or by tapping in a specific area of the infotainment bus.
### Via OBD connector
- [x] <b>1.</b> Read installed modules list 
- [x] <b>2.</b> Read long coding from a module (ex.: multimedia unit 5F)
- [x] <b>3.</b> Write long coding on a module
- [x] <b>4.</b> Read adaptation value from a module
- [x] <b>5.</b> Write adaptation value on a module without security access code
- [x] <b>6.</b> Write adaptation value on a module with security access code

## Automation scripts
- Work in progress :)
