Prerequisites: [[Motors Summary]], [[PWM]], [[MCU]], [[IC]]

A motor driver is an electronic circuit that acts as a bridge between a low-power controller (like a microcontroller) and a higher-power motor, allowing the controller to safely switch and control the motor’s voltage and current. Drivers usually provide a method for the client to command speed and direction.

> Some simple drivers only handle direction not speed.

The driver is passed power from a power source and signal from an MCU. Then it sends controlled power commands to the motor.

Drivers deal with switching power and so usually need heat sinks to release it.

![[Pasted image 20260309135510.png]]

The following is the circuit diagram and image of a h bridge driver, with a heat sink for a Brusged DC motor.