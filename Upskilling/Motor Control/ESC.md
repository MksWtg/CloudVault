Prerequisites: [[Driver]], [[BLDC]], [[Feedback]], [[PWM]]

An ESC (Electronic Speed Controller) for a BLDC motor is an electronic device that switches the motor phases in sequence and controls voltage/frequency, allowing precise control of speed and direction.

It’s basically the “driver” that makes a BLDC spin properly.

ESCs require additional wires for control and optionally feedback.

In the image below, the fat red and black wires are power in, the three black wires are power out to motor (which will be controlled so the motor spins the right way with control).

The three thin coloured wires are likely signal in. One is `5v` for the ESC itself, one is `GND` as reference and one is control, likely PWM.

![[Pasted image 20260309132323.png]]