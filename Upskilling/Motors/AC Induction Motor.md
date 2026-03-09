
Prerequisites: [[Magnetic Field]], [[DC Motor]], [[Alternating Current]], [[Electromagnetic Induction]], [[Induced Current]]

(Also known as asynchronous AC motor).

![[Pasted image 20260308175413.png]]

An AC induction motor works by converting electrical energy into mechanical energy using electromagnetic induction.

It has two main parts: the stator and the rotor.

The stator is the stationary part and has windings connected to an AC power supply. For a three phase motor, this power supply delivers 3 separate voltages 120 degrees out of phase. 

Even though the wires are all connected, because they connect in a 'Y' at a junction, the currents are different.

When AC flows through the stator windings, it produces a magnetic field that changes direction or rotates (RMF).

![[Pasted image 20260308183644.png]]

> The speed of the rotating magnetic field depends on the frequency of the AC. In a country since all AC has the same Hz, all AC devices have a magnetic field that rotates at the same speed (unless they modify this manually).


The rotor is the rotating part, usually a squirrel-cage design, and it is placed inside the stator’s magnetic field. The changing or rotating magnetic field induces a current in the rotor according to Faraday’s law of induction. This induced current in the rotor creates its own magnetic field (rotating currents induce magnetic fields) that interacts with the stator field, producing torque that causes the rotor to turn.

![[Pasted image 20260308183722.png]]

The rotor never reaches exactly the speed of the rotating magnetic field; the difference in speed is called slip and is necessary to maintain induction- if they moved in sync, without a difference in speed, there would be no induction (no relative change in flux). The rotor continues to turn, and this rotation is used to do mechanical work, such as driving a pump, fan, or conveyor.

> We can increase or decrease the speed of the rotor by increasing the strength of the RMF, e.g. by increasing stator voltage, or varying the supply frequency.

> Three-phase induction motors are inherently self-starting due to the rotating magnetic field (RMF) produced by the 3-phase supply.

 It’s Self-Correcting
- If the rotor lags too much: Relative motion increases → larger induced currents → stronger rotor field → more torque pulling it forward.
- If the rotor catches up a little: Relative motion decreases → smaller induced currents → less torque → rotor naturally stabilizes at a small lag (slip).

## Use Cases

Asynchronous or induction motors are simple, rugged, and low cost. They are self-starting, do not require brushes or special excitation, and are widely used in fans, pumps, compressors, conveyors, and household appliances. Their speed varies slightly with load, which is acceptable in most general-purpose applications. 


Induction motors are chosen for simplicity, reliability, and general-purpose use.