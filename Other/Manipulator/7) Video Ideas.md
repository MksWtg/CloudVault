
Finals:
1) demo for end users
	- x y z, r p y (cartesian jogging of end effector)
	- repeatability and accuracy (using 0.01 mm measuring device)
	- Inverse kinematics for user with controller
	- Web interface, showing parts like wifi widgets, visualization, telemetry etc.
	- show each end effector
		- camera with stream
		- gripper with environment/sim visualization
		- rgbd with scan and display
		- glove with triple gripper
2) demo for developers, show steps to add end effector (assuming you have an end effector)- use gripper and cam combo
	1) show programming backend (requirements: docker)
	2) show compile into docker with arm
	3) show programming frontend
	4) show usage- plugging in usb, attaching effector hardware software, electrical, power on
	5) go to frontend
3) how it works: hardware
	1) gearboxes, motors, drivers, link lengths, payload, statics, dynamics, FEA, simulation if necessary