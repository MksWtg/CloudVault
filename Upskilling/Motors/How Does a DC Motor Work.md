Prerequisites: [[The Motor Effect]], [[Circuit]], [[Current]], [[Current#Direct Current]], [[Fleming's Rules]]

![[Pasted image 20260301204211.png]]


A DC motor works by using the motor effect to turn electrical energy into mechanical motion.

When current flows through a coil of wire, the moving charges generate a magnetic field. If this coil is placed inside a magnetic field, each side of the coil experiences a magnetic force as the two fields interact.

Because the currents in opposite sides of the coil flow in opposite directions, the two sides of the coil experience opposite forces. This has a turning effect (torque) that makes the coil rotate.

A component called a commutator reverses the direction of the current every half turn. Here is how it works:

- The magnetic field moves from east to west
- Current flows clockwise through the armature (looking down). from the battery, the current flows through the brushes (little black blobs) onto the circle (commutator) then through the coil (armature) and back through the commutator, brush, into the negative. The commutator and armature both rotate. The brush is fixed. The brush has little springs or some kind of pushing mechanism to ensure it is always in contact with the commutator. It is usually made of something soft like carbon that wears away over time. This is to ensure continuous current transfer from a fixed component onto a moving one.
- Direction of current changes depending on which part of the coil you look at
	- For the top of armature (parallel to magnetic field), there is no force
	- For the left hand side of armature:
		- Current moves from bottom to top
		- Magnetic field moves from east to west
		- Force goes up out of page, by the left hand rule
	- For the right hand side of armature:
		- Current moves from top to bottom
		- Magnetic field moves from east to west
		- Force goes into the page, by the left hand rule
- The forces on either side of the armature moving in different directions creates a rotating/spinning force. This force acts on the armature- the wire along with the commutator, which is the little circle at the bottom. This is the principle of a motor.
- After the coil has rotated exactly 90 degrees, the (previously) left side of the commutator now touches the right brush and vice versa. This causes the current to be reversed, and the force to be reversed. So the armature keeps spinning. It always tries to put negative to positive and positive to negative in the two magnetic fields, but whenever it gets close the current switches, induced field switches and therefore a force continues pushing the motor.

The torque for the motor will look like $abs(\sin(t))$. Whenever 