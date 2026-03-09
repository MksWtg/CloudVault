Prerequisites: [[PWM]], [[Driver]], [[DC Motor]]

For an ordinary brushed DC motor with two terminals, PWM works by rapidly turning the voltage on and off across the motor. The motor’s speed depends on the duty cycle of the PWM signal:

- A higher duty cycle (more "on" time) means the motor gets more average voltage, so it spins faster.
- A lower duty cycle (more "off" time) reduces the average voltage, slowing the motor.

The motor’s inertia smooths out the rapid switching, so it responds as if it’s receiving a lower continuous voltage rather than a pulsed one.


To actually use PWM on a brushed DC you need:

- Microcontroller or PWM source Something like an Arduino, ESP32, or Raspberry Pi can generate the PWM signal
- Driver or transistor. You can’t usually drive the motor directly from the microcontroller because it can’t supply enough current. Common options are H bridge ICs like L293D. or a MOSFET.
- Power supply

STEPS

1. Connect the two motor terminals to the H-bridge output pins.
2. Connect the H-bridge power input to a suitable motor voltage supply.
3. Connect the H-bridge control inputs to the MCU GPIO pins.
4. Configure two MCU pins for direction control and one for PWM speed control.
5. Set the direction pins high/low to choose the motor rotation direction.
6. Output a PWM signal from the MCU to the H-bridge enable or PWM input pin to control speed.
7. Adjust the PWM duty cycle to increase or decrease the motor speed.
8. Optionally, add flyback diodes if the H-bridge doesn’t have built-in protection.
9. Test with low duty cycles first to ensure connections and motor response are correct.
