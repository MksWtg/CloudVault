Prerequisites: [[BLDC]], [[Motors Summary]]

The simplest way to power BLDCs and other 3 phase motors is by pulsing each phase to get the rotor to spin.

The voltage is on or off, blocky, so called block.

The back EMF grows then shrinks linearly, so this is also called trapezoid.

This is very simple control. It is good because it works, but bad because when a pulse stops or starts the torque is weak. This wavering torque is called torque ripple.

![[Pasted image 20260322173949.png]]