Prerequisites: [[Driver]], [[BLDC]], [[Feedback In Motors]], [[PWM]]

An ESC (Electronic Speed Controller) for a BLDC motor is an electronic device that switches the motor phases in sequence and controls voltage/frequency, allowing precise control of speed and direction.

It’s basically the driver that makes a BLDC spin properly. While a "dumb" driver does rapid on and off switching, the ESC is more complex.

> With a two-terminal brushed motor, current just flows back and forth through the single coil pair, and the motor’s mechanical commutator handles switching automatically. On and off is all that needs to be controlled. In a BLDC motor, the ESC must electronically time the switching (often six steps per electrical rotation) across three coils, sometimes using feedback from sensors or back-EMF detection, which adds both hardware and software complexity.

ESCs require additional wires for control and optionally feedback.

In the image below, the fat red and black wires are power in, the three black wires are power out to motor (which will be controlled so the motor spins the right way with control).

The three thin coloured wires are likely signal in. One is `5v` for the ESC itself, one is `GND` as reference and one is control, likely PWM.

![[Pasted image 20260309132323.png]]