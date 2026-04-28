Prerequisites: [[Source Code]]

Machine code are the lowest level of instructions that computers can execute directly.

Low level means the operations do simple things that are useless individually and must be combined to do useful work- instructions might be like add the value of register X to register Y and store the result in register Z or move the value in register X to register Y, or increment register Z.

A single instruction is a number, e.g. `A5` in hexadecimal. It is very difficult for humans to write machine code directly, so we normally write code in source code files and use other programs to convert source into machine code.

Machine code is machine specific- codes on one machine do different things to another machine. As opposed to source which is a high level specification and consistent across all machines.