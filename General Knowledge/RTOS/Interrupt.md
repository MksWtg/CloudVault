An interrupt is a signal that temporarily stops the CPU from executing its current instructions so it can immediately handle something more important.

When an interrupt occurs, the CPU saves its current state, switches to a special handler in the operating system (called an interrupt handler), and runs that code to deal with the event. After finishing, it restores the previous state and continues where it left off.

Interrupts are used for things like keyboard input, timers (for scheduling processes), disk I/O completion, and hardware events, allowing the OS to respond quickly without constantly checking devices in a loop.

Interrupts and Exceptions both alter program flow. The difference being, interrupts are used to handle external events (serial ports, keyboard) while exceptions are used to handle instruction faults, (division by zero, undefined opcode).

A trap or exception is a software-generated interrupt caused either by an error or a user request



ISR is a piece of kernel code that handles the interrupt
e.g. reading a pressed key

the interrupt vector is a lookup table in memory, every type of interrupt has an ID that maps to the right ISR so the CPU knows how to handle it