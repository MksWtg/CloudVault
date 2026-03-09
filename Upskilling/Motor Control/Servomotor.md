Prerequisites: [[Motors Summary]], [[PWM]], [[Feedback In Motors]], [[Driver]]

A servo motor (servo) is a motor combined with a feedback system and control electronics that allows precise control of position, speed, or torque. It usually receives a command signal (like a PWM pulse) and adjusts its shaft to match the desired position, automatically correcting any errors using feedback. Servo motors can be brushed or brushless, and they are widely used in robotics, RC vehicles, and automation where precise motion is needed.

## Hobby Servo

The below is a cheap hobby servo, these are usually DC. It receives signal and power. Although signal is a PWM, it is handled differently to an ordinary brushed DC motor. For a servo, PWM is a position command, not speed control. The pulse width (usually 1-2 ms in a 20 ms period) tells the servo the target angle, and the internal electronics drive the motor to that angle. 

The feedback system is contained within the servo- it is not provided to the client.

![[Pasted image 20260309134812.png]]

## Brushless Servo

![[Pasted image 20260309140034.png]]

This servo is based on a BLDC and provides feedback.

## Industrial Servo

![[Pasted image 20260309151954.png]]
High torque, rated for 3Nm, 7A, 1kW. It also uses a BLDC.

Industrial servos are just the motor + encoder. They require a separate servo drive/amplifier (like Beckhoff AX series) that performs the control loops and commutation.

An industrial servo motor like the Beckhoff AM1000 is basically a high-quality 3-phase brushless motor (BLDC/PMSM) with an encoder attached. By itself it does not perform control. The external servo drive handles commutation, current control, and the closed-loop position/speed control.

