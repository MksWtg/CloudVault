
Prerequisites: [[FOC]], [[Feedback In Motors]], [[Encoder]]

Closed loop and FOC are both methods of control. What is the difference?
- What is the same: they both used feedback, they are both closed loop- FOC is a subset of closed loop
	- When people say closed loop instead of FOC, it is implied to be an "ordinary" inferior closed loop system to FOC (FOC is an improvement over ordinary closed loop).
- What is the difference: ordinary closed loop uses trapezoidal/6 stage commutation.

## Comparison Table

Prerequisites: [[SVPWM]], [[SPWM]]

|                                                               | Open Loop | Closed Loop |
| ------------------------------------------------------------- | --------- | ----------- |
| 6 Stage (voltage is block/square wave, back EMF is trapezoid) |           |             |
| Sinusoidal (SPWM or advanced SVPWM)                           |           |             |
