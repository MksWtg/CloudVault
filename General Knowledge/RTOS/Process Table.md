
A process is a running instance of a program. E.g. chrome.exe or python

it becomes a process when OS loads instructions into memory from disk and executes them

it includes program code, CPU state, memory such as stack or heap, open files, pid, scheduling info

program is passive (just a file on disk) but process is active and currently executing

___

Process table is kernel DS which stores info about all active processes, such as PID, state, cpu register values, memory info

OS uses table to switch between processes and schedule CPU time

___
process states are:
- new
- ready
- running 
- waiting
- terminated
- zombie
- suspended

When