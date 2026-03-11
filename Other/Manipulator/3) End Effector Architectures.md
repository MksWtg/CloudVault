
# Assumptions

- End effector cannot contain compute module only mcu
- It is equally easy to make both modules into APIs
	- this means turning the client into an API (e.g. open gripper close gripper) and turning the base into an API (go to pose, get pose) are just as easy
## Option 1: Arm is a Service, End Effector Controls

*End Effector Reads Data and Calculates Pose*

EndEffector -> Base: Go To Pose X

benefits:
- easy architecturally
- easy for client (they write a main method, read data from their own hardware)
	- they only have to make one thing, the end effector

cons:
- mcu is not high bandwidth, cannot send lots of data to base for processing e.g. depth camera
- since all compute is happening on the end effector, it can't do anything advanced not sure of examples though

## Option 2: End Effector is a Service, Arm Controls

*Base Station Requests End Effector Data and Sends Instruction*

Base -> EndEffector: Requests Latest Sensor data
EndEffector -> Base:  Sends Latest Sensor Data
Base -> EndEffector: Go To Pose X

benefits:
- since all compute is happening on the base, 
	- 1) have access to compute module on base
	- 2) you have access to base data e.g. web interface, wifi- note technically we could also expose this through the base via api, but i feel like there is something wrong about using the base as a proxy and manually forwarding all method calls through via a custom framework. like the end effector (EE) shouldnt have to make http requests through the base.

cons:
- mcu is not high bandwidth, cannot send lots of data to base for processing e.g. depth camera
