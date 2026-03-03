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