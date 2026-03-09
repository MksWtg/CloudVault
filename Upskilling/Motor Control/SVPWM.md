Prerequisites: [[PMSM]], [[BLDC]], [[PWM]]

SVPWM, or Space Vector Pulse Width Modulation, is a method for generating the PWM signals used to drive three-phase motors, mainly permanent magnet synchronous motors (PMSM) and brushless DC (BLDC) motors.

It works by representing the three-phase voltages as a vector in a two-dimensional plane and approximating the desired sinusoidal voltages by switching the inverter in a precise sequence. This produces smoother currents, higher voltage utilization, lower torque ripple, and better efficiency compared to simple sinusoidal PWM. SVPWM is typically used in field-oriented control for PMSM and BLDC motors. It is not generally used for brushed DC motors, traditional stepper motors, or simple AC induction motors without vector control.
