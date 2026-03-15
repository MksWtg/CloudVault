Prerequisites: [[Steppermotor]], [[Driver]]

Microstepping is a technique used in stepper motor control where the driver divides each full step of the motor into many smaller steps by carefully controlling the current in the motor’s coils.

> Microstepping is generally considered a superior method of control (over ordinary stepping).
> You can settle and hold at a microstep, but it is less stable and less accurate than a full-step position.

Normally a stepper motor moves one fixed angle per step (for example 1.8° per step, which is 200 steps per revolution). In basic operation the driver fully energizes one phase and then the next, so the rotor jumps from one stable position to the next.

With microstepping, the driver does not switch coils fully on and off. Instead it gradually changes the current in the two motor phases so the magnetic field rotates smoothly. This is usually done with sine and cosine current waveforms.

> Microstepping does not require any specific hardware, it just utilizes basic stepper hardware. Microstepping ability is enabled/disabled in the driver.

For example, instead of switching like this:
1) phase A = 100%, phase B = 0%
2) phase A = 0%, phase B = 100%

The driver transitions through intermediate levels such as:
1) phase A = 100%, phase B = 0%
2) phase A = 92%, phase B = 38%
3) phase A = 71%, phase B = 71%
4) phase A = 38%, phase B = 92%
5) phase A = 0%, phase B = 100%

Each intermediate point becomes a smaller “microstep”.

Common microstepping divisions include:

- 1/2 step
- 1/4 step
- 1/8 step
- 1/16 step
- 1/32 step or finer

If a motor has 200 full steps per revolution and you use 1/16 microstepping, the controller can command:
200 × 16 = 3200 microsteps per revolution.

## Benefits of microstepping:

- smoother motion
- less vibration and noise
- finer position control

## Limitations:

- microsteps have less holding torque than full steps
