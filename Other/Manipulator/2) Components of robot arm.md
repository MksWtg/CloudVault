This list ignores any upskilling needed
1) Power distribution board
	1) Power in from wall (no battery)
	2) Power out to drivers, pi, lights
	3) Voltage, current and temperature sensors that feed to pi
	4) Slots for fuses
2) Closed loop drivers (FOC or not?)
	1) CAN for daisy chaining
	2) Built in absolute encoder
	3) STM chip for firmware
	4) Enables microstepping and closed loop control
3) Physical arm
	1) 3d printed links
	2) Motors
	3) Gearboxes
	4) Belts and pulleys
4) Pi
	1) High level control code, inverse kinematics for arm
	2) Runs web server that exposes web interface (can do joint control or end effector pose) and displays robot visualization
5) Custom end effectors (see [[6) End Effector Options]])
	1) gripper
	2) camera with gripper
	3) depth cam with scanning software

Interfaces:
1) A keyed clamp goes on the end of the shaft and has 4 mounting holes
2) Electrical interface: USB C
3) Software interface: users input a usb stick that has a file called "main.cpp" in it. This file can read: joint states, the usb device ls0 or whatever (representing the custom device they are plugging into the port), current controller readings from xbox controller and have access to the action client api to send the end effector to a post (including selecting which solution if there are many) or can write to the joint position/velocities. Can also read from web interface (see point #4).
4) Web interface: Can define custom html/css/js elements that get put into the web interface (TODO investigate a good interface for this to fit neatly into the UI, might make a basic component library). E.g. a custom button called "SCAN" and when users hit this button it searches for an object, scans it and generates an STL to print. web interface also provides 1) a way to connect to a network and 2) a way to get data, logs, photos, etc. off the arm. It should also give access to htop style stats ram etc.

i need a medium quality gearbox reducer. here are my requirements:
- must be dual shaft, or otherwise be easy to adjust to make it dual shaft
- will use it for a nema stepper, so no torque requirements. under 50x50mm size
- total cost of base gearbox + adjustments under 150 aud
- ratio roughly 30 : 1 - backlash less than 10 arcmin

Interface prompt:
im making a robot arm for a client and want to give the client full complete customization of any end effector they want, that is controllable both data and signal through the main computer. but they cant program the main computer directly. there has to be some ioc/other setup so the user can do whatever hardware and software they want to write code to control both the arm and read/write from the end effector.

