Prerequisites: [[PMSM]], [[BLDC]], [[PWM]], [[Inverter]], [[SPWM]]

SVPWM, is a method for converting a steady state DC signal into AC. It is like SPWM but better.

SPWM generates PWM signals to approximate an AC sinusoidal waveform for all 3 phases.

SVPWM computes the final vector representing the net sum of the three phases. Then it does the pwm for this waveform.

Remember how effectiveness (torque) comes from current and current comes from voltage. And voltage is a differential. For SPWM this differential is at a max $\frac{\sqrt{3}}{2}$ which is $0.866$ or 85%. SVPWM does some shifting of the waveform to make it more efficient.

~~The thing is, sum(pwm(phases)) should equal pwm(sum(phases)) as the quality of pwm increases. So these techniques should be exactly the same. So there is a fallacy.~~