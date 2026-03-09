Prerequisites: [[DC Motor]], [[BLDC]]

PWM, or Pulse Width Modulation, is a technique used to control the amount of power delivered to electronic devices by rapidly switching a signal on and off. The duty cycle- the proportion of on time to the total cycle time, determines the effective voltage or power. It’s commonly used in applications like motor speed control, LED dimming, and voltage regulation.

![[Pasted image 20260309132833.png]]

(on white background:)

![[Pasted image 20260309132822.png]]

## PWM and Brushed DC Motors

For an ordinary brushed DC motor with two terminals, PWM works by rapidly turning the voltage on and off across the motor. The motor’s speed depends on the duty cycle of the PWM signal:

- A higher duty cycle (more "on" time) means the motor gets more average voltage, so it spins faster.
- A lower duty cycle (more "off" time) reduces the average voltage, slowing the motor.

The motor’s inertia smooths out the rapid switching, so it responds as if it’s receiving a lower continuous voltage rather than a pulsed one.

If you want, I can also make a simple diagram showing PWM on a 2-terminal motor—it makes it really clear visually. Do you want me to do that?