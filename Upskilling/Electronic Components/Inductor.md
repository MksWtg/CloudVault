Prerequisites: [[Inductance]]

An inductor is a passive electrical component designed to store energy in a magnetic field when current flows through it. Essentially, it’s a coil of wire that resists changes in current due to its inductance.

![[Pasted image 20260308165200.png]]

## Use Case

A common use case for an inductor is filtering high-frequency noise on a power supply line to an MCU.

- For example, suppose you have a switching regulator powering a microcontroller. Switching regulators generate high-frequency ripple and spikes. If you place a ferrite bead or small inductor in series with the `Vcc` line, it blocks the high-frequency current components from reaching the MCU while still allowing DC to flow. This reduces the chance of the MCU misbehaving due to voltage spikes.
- Another example is in LC filters for sensitive analog signals. You might put an inductor in series with the signal line and a capacitor to ground after it. The inductor resists sudden changes in current (high-frequency noise), and the capacitor shunts remaining noise to ground. This combination is widely used in sensor inputs, audio circuits, or RF circuits.

So the general pattern is: use an inductor whenever you want to resist or block high-frequency currents from propagating, especially on power or signal lines.