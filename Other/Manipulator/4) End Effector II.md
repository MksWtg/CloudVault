My arm priorities:
- smooth motion and accuracy
- small
- good support for devs/usability

```
context: i have built a robot arm and now i have to give instructions to clients to build end effectors for it. limitation: i can only expose one usb port for the end effector. now if it were a custom gripper, they would be able to control both the gripper and the arm via an api that i could write. but if it were a depth camera for example the single port would get used up by the camera with no room for code to control the arm. so my strategy is the base station controls the arm. the user controls the arm and end effector by putting a usb stick with code onto it onto the arm that calls the high level api. but it is not clear if the driver needs to be packaged with the usb, and if the computer can be set up to read the driver from the usb or if the appraoch will change based on the actual end effect e.g. custom gripper or off the shelf depth camera. does this make sense?
```


```
so the bottom line is there is no truly perfect way to do this, because the user could just plug in a dongle or some other usb in as end effector which effectively doesn't do anything.

additionally, the user might have an end effector that exposes some API through usb, and the user might call api endpoints with bad params that dont make sense.

lets assume the user is doing the best they can.

EITHER 1) the end effector is supported by linux by default driver, like usb webcam. we must support this and allow programmatic access as linux would normally, which should be easy

2) the user is using an off the shelf device like rgbd realsense with its own library. they have the lib, and give it to us so we can let them use it because their code needs it. note that this section could also apply to a driver, but i cant think of any end effector usb devices that need their own driver.

3) a usb CDC device that has defined methods running on the mcu to read/write and they call these.

how can i handle all three of these cases
```

```
i dont understand. lets say:

1) the user code is guaranteed to call my robot API which exists off the usb, on my base

2) the user code is provided to robot on base via usb stick

3) when robot powers on, it starts executing from the base

4) the user code has some dependencies e.g. on realsense sdk

what instructions should i give the user so they can prepare themselves to run code on the arm
```

```
i dont like the python specific or cpp specific methods because the user example might not be python or cpp specific. I think this is best: docker container, they can have any esoteric dependencies installed on it. three questions:

1) if it is running on a pi, do they need to do a specific arm build for the image
2) can they run the image off the usb instead of copying it over to the pi
3) can they call my api from the pi? actually this last part is the most complex, because they dont have control over the code. my arm starts up, does homing, and then hands control to them. or using ioc, calls the client's main method. so im not sure if this works
```

```
lets say on boot i have a main method run that does homing. this method also has a state machine etc. and monitoring, if anything bad happens this should resume control. how can i run the user's code "inside" my code. also allowing the user to call my api?
```

```
please confirm yes/no to each:
- on boot main method starts, homing happens
- AFTER that, it spins up docker container. docker container can see the usb device end effector, regardless of what type it is, and therefore user code can query it to do things. if anything bad happens, docker container is shut down by main method. docker container can also talk to robot api server via tcp.
- user code sends api requests to robot, queries usb device.
- when user code finishes, it emits some signal and main method shuts down container

```

```
1) how to configure docker to see usb device regardless of whta device, and see the robot api
2) are the robot api and the main method the same program or different programs or up to me?
3) how to shut down container from main method (pseudocode)

```

```
so i have the following processes:
- html css js static telemetry web server
- lightweight custom high level code that i will write in c/cpp for inverse kinematics and api
- main controller/state machine (also lightweight c process)
- docker container (can include anything and everything that the client puts in, but i can kindly request that they keep it to a certain size).

what can i expect in terms of ram, storage, cpu? i want to minimize everything and keep it as lightweight as possible
```

## Repo List (Production Only)

- FOC
	- big driver and small driver if different, should both use the same repo
- docs on arm
	- how it works
	- how to build and end effector
- end effector examples
	- 1) realsense scanner
	- 2) simple cam
	- 3) ai cam with gripper
- main control loop
	- spin up, state machine, calibrate, launch container, etc., propagates signals from 
- high level IK code + API for this
- telemetry (this has to be separate from main control loop because we give telemetry to users to test, along with SDK).
	- visualization
	- optional widgets
		- file explorer to see where code is for debugging
			- device explorer to see when end effector is plugged in e.g. CDC serial, UVC camera, custom usb thing maybe, HID devices
		- process explorer to see docker container idk
		- wifi widget to connect to internet idk
		- colour of robot lights- could have a controller for this (new repo maybe)
	- telemetry (e.g. current, voltage from power board, maybe even current, voltage, temp from FOC. Also position from FOC for visualization.), logs
	- logs all api calls and their results
	- custom pages for sending actions, e.g. camera page, scan page
- sdk for development- provide API that connects to simulation and the simulation itself- can share visualization module with telemetry.
	- question: how do we have the actual robot api and the simulation topic hot swappable- custom ROS-like framework? one answer, could package a simulation server that runs on the same port as the arm API, so only one runs at once. For dev you can run the thing yourself, and for 


## Maybe test
- baby foc
- baby 6dof IK