Prerequisites: Motor, [[PWM]], [[MCU]], [[IC]]

A motor driver is an electronic circuit that acts as a bridge between a low-power controller (like a microcontroller) and a higher-power motor, allowing the controller to safely switch and control the motor’s voltage and current. It often includes transistors or an H-bridge to handle direction and speed control via signals like PWM.

> Some simple drivers only handle direction not speed.

The driver is passed power from a power source and signal from an MCU. Then it sends controlled power commands to the motor.

Drivers deal with switching power and so usually need heat sinks to release it.