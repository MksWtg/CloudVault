
1) ~~Formalize rough requirements~~
2) Properly understand FOC algorithm
3) Understand high level driver steps for BLDC FOC
4) Understand high level driver steps for NEMA stepper FOC

Separately:
5) Practice making circuits. Send to reddit for review.
	1) USB powered LED flashlight
	2) Power distribution board
	3) Basic H bridge driver for brushed
	4) Simple ESC driver (open loop)
	5) Simple closed loop driver for ESC
	6) Lighting ring (with control/device pass through maybe)
	7) Microcontroller with USB port
	8) Air pressure sensor from demo video
	9) IMU data from PCB
6) Draft list of hardware components and their roles based off my limited understanding for closed loop BLDC FOC
	1) Same for microstepping Stepper
	2) Same for Stepper FOC
7) Draft list of firmware components and their roles based off my limited understanding for closed loop BLDC FOC
	1) Same for microstepping stepper
	2) Same for Stepper FOC

Then:
8) Practice uploading code to STM32 and writing STM32 code (follow [[10) STM32 Upskilling]])
9) Macro keypad (STM32 + custom PCB): A small 3–6 button keypad that sends programmable shortcuts to your PC.
10) CAN: read and understand basics of the protocol, look at samples
11) ARDUINO CAN:
	1) Initialize CAN controller
	2) Listen for all CAN frames
	3) Print them to serial
12) STM32 CAN messager
	1) Create two STM32 boards communicating over CAN where one sends sensor data and the other receives it.
	2) Read temperature or potentiometer via ADC and Send CAN message every 100 ms

Now onto FOC:
13) Read ALL FOC repos (firmware) and make list of hardware components (by looking at pcb files) to better understand what is involved
	1) Start with simple FOC (for BLDCs and steppers, sensored)
	2) Then VESC (for BLDCs, supports sensorless)
	3) Then Odrive (sensored)
	4) Then XDrive (what penguin used)
	5) Penguin's firmware and gerber himself
		1) Now that we understand PCBs and firwmare, read the rest of his PCBs and make a list of what they are for. E.g. REF unit. He said to include extra pcbs for redundancy and speed, so make sure we figure out what he meant. For example, what is going on  here:
		2) Looks like there are three: ![[Pasted image 20260313120431.png]]
		![[Pasted image 20260313115626.png]]

Finally:
14) Make the actual controller. Requirements:
	1) Magnetic absolute encoder
	2) Microstepping (ideally 1/64)
	3) FOC control
	4) CAN communication
	5) Daisy chain control and power
	6) Pass back current and voltage and temperature
	7) [OPTIONAL] Pass back position and velocity

ALSO list of hardware we should have gotten:
1) clear PLA for printing cases for driver
2) heatsinks for driver (duh)
3) reflow board + reflow paste
4) new soldering iron and solder maybe