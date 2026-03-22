
Prerequisites: [[FOC]], [[Feedback In Motors]], [[Encoder]]

Closed loop and FOC are both methods of control. What is the difference?
- What is the same: they both used feedback, they are both closed loop- FOC is a subset of closed loop
	- When people say closed loop instead of FOC, it is implied to be an "ordinary" inferior closed loop system to FOC (FOC is an improvement over ordinary closed loop).

## FOC 

know the rotor electrical angle
measure phase currents
control the current (using PID) relative to that angle so that the current vector is oriented correctly with respect to the rotor field