Prerequisites: [[Capacitance]], [[Electronic Components]], [[Electric Field]], [[Voltage]], [[Electric Charge]]

A capacitor is the device that exhibits that property capacitance.

A capacitor is an electrical component that stores energy in an electric field. It typically consists of two conductive plates separated by an insulating material called a **dielectric**. When a voltage is applied across the plates, positive charge accumulates on one plate and negative charge on the other, creating an electric field that stores energy.

![[Pasted image 20260308135551.png]]

In the image, when the two pieces of metal are separated and connected to terminals of a battery, the `+` terminal of the battery attracts electrons making that plate `+`. While the `-` plate collects electrons that are repelled by the `-` terminal.

This continues until the plates reach a state of equilibrium- the `+` plate stops repelling electrons and becomes so positive it attracts electrons just as much as the `+` terminal. Same for `-`.

The energy is stored in the electric field between the plates, not in the electrons themselves. After reaching a state of equilibrium, when the battery is removed, the energy will remain in the EF.

## The Dielectric

The dielectric is the insulating material placed between the two plates of a capacitor.

Its main purposes are:
- Prevent direct current flow between plates (so electrons don’t just jump across).
- Increase capacitance without changing the plate area or spacing too much.

Technically, a capacitor can work with air or vacuum as the dielectric, but the capacitance is smaller.

- The dielectric polarizes in the electric field: all the molecules rotate so the `+` ends align with negative and `-` with positive
- This internal field opposes the field from the plates
- So the net field is smaller than it would have been, so charge is fixed and voltage decreases so capacitance increases.
## How Long Does it Take to Reach Equilibrium

The charging follows an exponential equation:

$$V_C​(t)=V_{battery}​(1−e^{−t/RC})$$

$$I_C{T} = \frac{V_{battery}}{R}e^{-t/RC}$$

Technically, the capacitor never reaches 100% in finite time, because the exponential only approaches the battery voltage asymptotically


