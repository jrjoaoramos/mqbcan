# MQB Platform CAN
This projects aims to identify and analyse the CAN buses that lie in the Volkswagen Group MQB Platform based cars.
## Introduction
There are plenty cars based on this famous platform developed by VAG. They share the same base that allows developers and make them pleasant to research into them and make spectacular things. As such, this repo shares some of the findings that the community find.

## Target cars
The examples found here can be applied, theoretically, to any MQB car. Although, considering that we don't have access to all of them, currently they are tested in:

- Seat Leon 5F

They can also be applied, of course, to:
- Audi A3 8V
- Volkswagen Golf MK7

## Current state
Currently there are being taken dumps from existing applications for common OBD adapter such as VAS, VCDS and VAG CAN PRO. Based on them, the CAN messages are analysed and then replicated. With those messages, there is the possibility to aggregate all the functions in our custom OBD adapters and implement new different features.

## How to start
In order to take dumps of CAN buses, there may be required some special devices. Some OBD-compliant softwares already allow us to record the messages that flow from the device to the car, but others are very closed and restrict. As such, there may be needed on of the following adapters or similar.

### CAN-BUS adapters
- CAN-BUS Shield V2.0 (http://wiki.seeedstudio.com/CAN-BUS_Shield_V2.0)
![alt text](https://github.com/SeeedDocument/CAN-BUS-Shield-V2.0/raw/master/img/CAN_BUS_Shield_V2.jpg)

- USB CAN Analyzer (https://www.seeedstudio.com/USB-CAN-Analyzer-p-2888.html)
![alt text](https://statics3.seeedstudio.com/seeed/file/2017-06/bazaar487719_1.jpg)

- Serial CAN-BUS Module based on MCP2551 and MCP2515 (https://www.seeedstudio.com/Serial-CANBUS-Module-based-on-MCP2551-and-MCP2515-p-2924.html)
![alt text](https://statics3.seeedstudio.com/seeed/file/2018-08/bazaar891352_img_2945a.JPG)

