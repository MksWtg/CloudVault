This list ignores any upskilling needed
1) Power distribution board
	1) Power in from wall (no battery)
	2) Power out to drivers, pi
	3) Voltage, current and temperature sensors that feed to pi
2) Closed loop drivers
	1) CAN for daisy chaining
	2) Built in absolute encoder
	3) STM chip for firmware
3) Physical arm
	1) 3d printed links
	2) Motors
	3) Gearboxes
	4) Belts and pulleys
4) Pi
	1) High level control code, inverse kinematics for arm
	2) Runs web server that exposes web interface (can do joint control or end effector pose) and displays robot visualization