Prerequisites: [[PMSM]], [[BLDC]], [[Driver]]

Stepper motors (steppers) are their own category of motor. They are not simply BLDC, PMSM, AC induction, or brushed DC motors, although they share some similarities with brushless permanent-magnet motors.

They are most closely related to BLDC/PMSM motors but are designed to run in open-loop step control rather than continuous commutation.

A stepper motor is an electric motor that moves in small, precise steps instead of spinning continuously like a normal motor. 

- Each electrical pulse sent to the motor causes the shaft to rotate by a fixed angle called a step.
- By sending a specific number of pulses, a controller can move the motor to an exact position. 

In a typical stepper motor, the permanent magnets are on the rotor (the inside rotating part), while the stator (the outside) contains electromagnetic coils.

The coils are energized in a sequence so the rotor moves from one position to the next. Because the position corresponds to the number of pulses sent, they are often used without feedback sensors.

![[Pasted image 20260309152720.png]]

> Stepper motors require a dedicated stepper driver that energizes the motor phases in sequence. A typical 2-phase stepper driver contains two H-bridges, one for each phase winding. The driver precisely controls the current in each coil and switches them in a sequence to create the stepping motion.

## Use Case

 They are commonly used in devices that need accurate positioning, such as 3D printers, CNC machines, and robotics.



