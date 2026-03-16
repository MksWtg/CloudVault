Prerequisites: [[SVPWM]], [[Motors Summary]] 

Also known as Vector control.

![[Pasted image 20260316202330.png]]

I_Q ref is the quadrature current, that is the goal current we want that determines how much torque we want.

We start by reading the three phase current actual value. We convert it to alpha beta axes using the clarke transform.

We start by reading theta from the magnetic encoder. 
We also read 
