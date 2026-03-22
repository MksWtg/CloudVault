Prerequisites: [[BLDC]], [[Motors Summary]]

The simplest way to power BLDCs and other 3 phase motors is by pulsing each phase to get the rotor to spin.

This control scheme has many names

- The voltage is on or off, blocky, so it is sometimes called block control.
- The back EMF grows then shrinks linearly, so this is also called trapezoidal control/commutation.
- There are 3 phases and each phase alternates between positive or negative (two stages) so there are 6 steps in total. So this is also called 6 step/six step commutation.

This is very simple control. It is good because it works, but bad because when a pulse stops or starts the torque is weak. This wavering torque is called torque ripple.

![[Pasted image 20260322173949.png]]