Prerequisites: [[Steppermotor]], [[Driver]]

Microstepping is a technique used in stepper motor control where the driver divides each full step of the motor into many smaller steps by carefully controlling the current in the motor’s coils.

Normally a stepper motor moves one fixed angle per step (for example 1.8° per step, which is 200 steps per revolution). In basic operation the driver fully energizes one phase and then the next, so the rotor jumps from one stable position to the next.

With microstepping, the driver does not switch coils fully on and off. Instead it gradually changes the current in the two motor phases so the magnetic field rotates smoothly. This is usually done with sine and cosine current waveforms.

> Microstepping does not require any specific hardware. 

For example, instead of switching like this:
phase A = 100%, phase B = 0%
phase A = 0%, phase B = 100%

The driver transitions through intermediate levels such as:
phase A = 100%, phase B = 0%
phase A = 92%, phase B = 38%
phase A = 71%, phase B = 71%
phase A = 38%, phase B = 92%
phase A = 0%, phase B = 100%

Each intermediate point becomes a smaller “microstep”.

Common microstepping divisions include:

1/2 step

1/4 step

1/8 step

1/16 step

1/32 step or higher

Example:
If a motor has 200 full steps per revolution and you use 1/16 microstepping, the controller can command:
200 × 16 = 3200 microsteps per revolution.

Benefits of microstepping:

smoother motion

less vibration and noise

finer position control

Limitations:

microsteps have less holding torque than full steps

real positional accuracy does not scale perfectly with the number of microsteps

In short, microstepping works by smoothly varying the current in the stepper motor’s two phases so the rotor can move in many smaller increments instead of jumping one full step at a time.