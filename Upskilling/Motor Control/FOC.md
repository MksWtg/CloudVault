Prerequisites: [[SVPWM]], [[Motors Summary]] 

Also known as Vector control.

![[Pasted image 20260316202330.png]]
> In a BLDC, windings are on stator and permanent magnets are on roto
I_Q ref is the quadrature current, that is the goal current we want that determines how much torque we want.

We start by reading the three phase current actual value. We convert it to alpha beta axes using the clarke transform.

We then read theta (angle of rotor) from the magnetic encoder. We rotate the actual current on alpha beta axis by the angle
