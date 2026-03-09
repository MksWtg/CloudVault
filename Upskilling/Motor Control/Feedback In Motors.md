
Prerequisites: [[BLDC]]

Feedback in motors is information sent from the motor back to the controller about its current state, like speed, position, or torque.

Common feedback types include encoders (measure rotation or position), tachometers (measure speed), and Hall sensors (detect rotor position in BLDC motors). The controller uses this feedback in a closed-loop system to adjust voltage, current, or PWM to maintain the desired performance. Without feedback, the motor runs open-loop, so speed or position can drift under varying loads. Essentially, feedback allows precise control and stability, making applications like robotics or CNC machines possible.

## Open Loop vs Closed Loop Control

- Open-loop control drives the motor without monitoring its output; the controller assumes the motor follows the input commands, so speed or position can vary under load.
- Closed-loop control uses feedback from sensors to adjust the input continuously, keeping the motor at the desired speed or position.

- Open-loop is simpler and cheaper but less precise.
- Closed-loop is more complex and costly but ensures accurate and stable performance.