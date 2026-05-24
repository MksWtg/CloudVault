
A **Process Control Block (PCB)** is a data structure maintained by the OS for every process, storing all information about it — including process ID, state, CPU registers, memory limits, and scheduling info.

It acts as the **identity card of a process**, allowing the OS to save and restore a process's context during context switching so execution can resume correctly later.do

More info:
```
When CPU switches to another process, the system must save the state of the current process and load the new state for the new process via a context switch • Context of a process represented in the PCB (Process Control Block) • Context-switch time is overhead; the system does a non-useful work while switching • The more complex the OS and the PCB ➔ the longer the context switch • Time dependent on hardware support • Some hardware provides multiple sets of registers per CPU ➔ multiple contexts loaded at once
```