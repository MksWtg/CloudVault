Prerequisites: [[DC Motor]], [[PWM]], MCU, IC

A motor driver is an electronic circuit that acts as a bridge between a low-power controller (like a microcontroller) and a higher-power motor, allowing the controller to safely switch and control the motor’s voltage and current. It often includes transistors or an H-bridge to handle direction and speed control via signals like PWM.
## Context: Controlling a DC Motor with PWM
For an ordinary brushed DC motor with two terminals, PWM works by rapidly turning the voltage on and off across the motor. The motor’s speed depends on the duty cycle of the PWM signal:

- A higher duty cycle (more "on" time) means the motor gets more average voltage, so it spins faster.
- A lower duty cycle (more "off" time) reduces the average voltage, slowing the motor.

The motor’s inertia smooths out the rapid switching, so it responds as if it’s receiving a lower continuous voltage rather than a pulsed one.


To actually use PWM on a brushed DC you need:

- Microcontroller or PWM source Something like an Arduino, ESP32, or Raspberry Pi can generate the PWM signal
- A component called a **driver**: You can’t usually drive the motor directly from the microcontroller because it can’t supply enough current. Common options are H bridge ICs like L293D.