Prerequisites: [[DC Motor]], [[Back EMF in DC Motors]], [[Current]]

How does the current vary in DC motors?
## Start

We know due to [[Back EMF in DC Motors]] that there is a large spike at $t= 0$ that decays exponentially as back EMF builds.

## No Load

When the motor is spinning freely with no external load, the rotor speed is high and the back EMF is almost equal to the applied voltage. The net voltage across the windings is small, so the current is low and steady, just enough to maintain motion against friction and other minor losses. This current remains relatively constant as long as the motor is running unloaded and the applied voltage doesn’t change.

## Load

If a mechanical load is applied, the rotor slows slightly, reducing the back EMF. This increases the net voltage across the windings and the current rises to provide the extra torque needed to overcome the load. As the rotor accelerates back toward a new steady-state speed, the current gradually stabilizes at a higher value appropriate for the load.

## Big Load

If the load changes suddenly, the rotor speed can drop abruptly, which immediately reduces the back EMF. The net voltage rises, causing a brief spike in current to supply the torque needed to resist the sudden load. The motor then accelerates toward a new steady speed, and the current drops to the new steady-state level for that load.

## Load Removed

If the load on a DC motor is abruptly removed, the situation reverses compared to adding a load. The rotor suddenly has much less torque resisting its motion, so it tends to accelerate rapidly. As the speed increases, the back EMF rises quickly because back EMF is proportional to rotor speed. This higher back EMF reduces the net voltage across the windings, which in turn causes the current to drop sharply, often to a value lower than the no-load current before the load was applied.
