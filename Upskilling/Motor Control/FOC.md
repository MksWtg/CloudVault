Prerequisites: [[SVPWM]], [[Motors Summary]] 

Also known as Vector control.

![[Pasted image 20260316202330.png]]
> In a BLDC, windings are on stator and permanent magnets are on rotor

> in a DC motor brushed, windings are on rotor and permanent magnet is on stator.


I_Q ref is the quadrature current, that is the goal current we want that determines how much torque we want.

We start by reading the three phase current actual value. We convert it to alpha beta axes using the clarke transform.

We then read theta (angle of rotor) from the magnetic encoder. We rotate the actual current on alpha beta axis by the theta to get the actual direct and quadrature currents.

Pass through low pass filter to remove high frequency noise.

Now we have Iq and Iq ref
We have Id and Id ref (0, or negative if using field weakening)

we use two PI controllers (TODO: why no D?) to calculate the voltages (TODO: this is voltage right? since voltage drives current) we need (Ud and Uq). Then we pass it back through the inverse park and inverse clarke transform to figure out the voltage we need for the three phases.

We use SVPWM to convert this voltage into the waveform the BLDC can use -> higher PWM frequency means higher resolution. Higher duty cycle means more voltage (comes from inverse clarke).

the svpwm is just the control signal, it still needs to go to a physical inverter circuit to power bldc.


| Thing          | Responsible for                              |
| -------------- | -------------------------------------------- |
| PWM/SPWM/SVPWM | %Voltage. SVPWM is more efficient than SPWM. |
|                |                                              |
