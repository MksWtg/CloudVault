Prerequisite: [[PMSM]], [[Back EMF]]


A BLDC motor, or Brushless DC motor, is very similar to a PMSM because it also has permanent magnets on the rotor and three-phase windings in the stator. But there are differences as it runs on DC.

![[Pasted image 20260309111652.png]]

The main difference is in how it is controlled.

In a BLDC motor, the controller (a physical electronic device that manages the currents going into the motor’s stator windings) switches current through the stator phases in a stepwise sequence based on rotor position, creating a magnetic field that moves in discrete steps.

![[Pasted image 20260309130854.png]]
In the above diagram, as the rotor (on the outside) aligns with coil A, which is currently energized, then A will be deenergized and coil B is energized. When the rotor aligns with coil B, coil B will be deenergized and C will be energized.

![[Pasted image 20260309131032.png]]

These waveforms enable continuous rotation, controlled electronically.

Think of it like donkey and carrot, the donkey (rotor) keeps trying to reach the carrot. But the carrot (stator magnetic field) keeps moving ahead of the donkey (due to the controller energizing the right coils).

![[Pasted image 20260309131147.png]]

This can be improved by passing the same polarity current through the coil behind the coil where the rotor is to "push" it from behind with repulsion.

![[Pasted image 20260309123734.png]]

This usually produces trapezoidal or square-shaped currents. In a PMSM, the controller drives the stator with smooth sinusoidal currents, producing a continuously rotating magnetic field.

