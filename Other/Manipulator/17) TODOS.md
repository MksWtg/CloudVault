
Do derivation that motor speed depends only on voltage

Do pole maths for control theory, transfer functions


## Progress
1) Driver
2) CAD arm parts
3) Write the simulation
4) 
5) Print arm parts + wiring
6) CNC arm parts


## Driver List

From easiest to hardest


|                     | Firmware | FOC | Driver  | Hardware | Daisy chaining | Link                                             |
| ------------------- | -------- | --- | ------- | -------- | -------------- | ------------------------------------------------ |
| SimpleFOC board     | ✅        | ✅   |         |          | ❌              |                                                  |
| Penguin with XDRIVE | ✅        | ✅   |         |          | ✅              |                                                  |
| MKS Servo C         | ✅        | ✅   |         |          | ✅              |                                                  |
| Things by josh      | ✅        | ❌   | TMC2209 |          | ❌              | https://github.com/joshr120/PD-Stepper/tree/main |
| ODrive              | ✅        | ✅   |         |          | ❌              |                                                  |
| VESC + Simple focer | ✅        | ✅   |         |          | ❌              |                                                  |
I saw a driver somewhere that referenced `bldc` presumably vesc bldc.