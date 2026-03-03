
# Assumptions

End effector cannot contain compute module only mcu
## Option 1: Arm is a Service, End Effector Controls

Base->EndEffector: Requests Latest Sensor data
EndEffector->Base:  Sends Latest Sensor Data
Base->EndEffector: Go To Pose X

benefits:
- easy architecturally
- easy for client (they write a main method, read data from their own hardware)

cons:
- mcu is not high bandwidth, cannot send lots of data to base for processing e.g. depth camera

EndEffector->Base2: Go To Pose