This list ignores any upskilling needed
1) Power distribution board
	1) Power in from wall (no battery)
	2) Power out to drivers, pi
	3) Voltage, current and temperature sensors that feed to pi
	4) Slots for fuses
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
5) Custom end effectors
	1) gripper
	2) camera with gripper
	3) depth cam with scanning software

Interfaces:
1) A keyed clamp goes on the end of the shaft and has 4 mounting holes
2) Electrical interface: USB C
3) Software interface: users input a usb stick that has a file called "main.cpp" in it. This file can read: joint states, the usb device ls0 or whatever (representing the custom device they are plugging into the port), current controller readings from xbox controller and have access to the action client api to send the end effector to a post (including selecting which solution if there are many) or can write to the joint position/velocities. Can also 