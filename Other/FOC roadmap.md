
Question: how come FOC looks easy on paper yet there are so many implementations?

# The math is tiny. The system is huge.

The _core_ FOC math fits on a whiteboard:

1. Measure phase currents
    
2. Clarke transform (abc → αβ)
    
3. Park transform (αβ → dq)
    
4. Run PI control on Id and Iq
    
5. Inverse Park
    
6. Space Vector PWM
    

That part is small.

What differs between implementations is everything around it:

- ADC configuration
    
- Current sensing method
    
- Encoder interface
    
- PWM hardware
    
- Timer synchronization
    
- Dead-time insertion
    
- Fault detection
    
- Startup logic
    
- Calibration
    
- State machine
    
- Communication interface
    
- Field weakening
    
- Sensorless estimation
    
- Thermal protection
    
- Overcurrent handling
    
- Bootloader
    
- Hardware abstraction layer
    

That’s the real code.