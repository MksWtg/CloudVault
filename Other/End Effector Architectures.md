
# Assumptions

- End effector cannot contain compute module only mcu
- It is equally easy to make both modules into APIs
## Option 1: Arm is a Service, End Effector Controls

*End Effector Reads Data and Calculates Pose*

EndEffector -> Base: Go To Pose X

benefits:
- easy architecturally
- easy for client (they write a main method, read data from their own hardware)

cons:
- mcu is not high bandwidth, cannot send lots of data to base for processing e.g. depth camera
- since all compute is happening on the end effector, it can't do anything advanced not sure of examples though

## Option 2: End Effector is a Service, Arm Controls

*Base Station Requests End Effector Data and Sends Instruction*

Base -> EndEffector: Requests Latest Sensor data
EndEffector -> Base:  Sends Latest Sensor Data
Base -> EndEffector: Go To Pose X

benefits:
