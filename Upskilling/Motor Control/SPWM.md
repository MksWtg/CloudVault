Prerequisites: [[PMSM]], [[BLDC]], [[PWM]], [[Inverter]]

SPWM stands for Sinusoidal Pulse Width Modulation. It is one of the simplest methods used to generate three-phase AC voltages from a DC source in motor drives.

In SPWM, the idea is very straightforward. You want the motor phases to receive sinusoidal voltages. Since the inverter switches can only turn fully on or off, SPWM creates pulses whose average value follows a sine wave.
![[Pasted image 20260313215424.png]]
![[Pasted image 20260313215410.png]]

For a three-phase motor, three sine reference signals are used. They are identical in shape but shifted by 120 degrees. The inverter outputs pulsed voltages that appear very close to sinusoidal currents in the motor windings.

The switching frequency of the triangular carrier is usually much higher than the motor electrical frequency. For example, the carrier might be 10 kHz while the motor frequency might be 50 Hz. Because of this, the motor inductance smooths the pulses and the current becomes nearly sinusoidal.

SPWM is simple to understand and easy to implement in microcontrollers or analog circuits. It was widely used in early motor drives.

SPWM is not that efficient, there are more efficient ways to invert a DC signal.