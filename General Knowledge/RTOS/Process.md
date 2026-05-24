
A process is a running instance of a program. E.g. chrome.exe or python

it becomes a process when OS loads instructions into memory from disk and executes them

it includes program code, CPU state, memory such as stack or heap, open files, pid, scheduling info

program is passive (just a file on disk) but process is active and currently executing

___

Process table is kernel DS which stores info about all active processes, such as PID, state, cpu register values, memory info

OS uses table to switch between processes and schedule CPU time

___
process states are:
- new: admitted to ready queue and is considered by scheduler (sometimes not yet in queue)
	- OS allocating memory
- ready: waiting in ready queue
- running: actively executing, can transition into ready if preempted
- waiting
- terminated
- zombie
- suspended

When is entry removed from table? all of these need to happen
- when process terminates using exit
- when the kernel marks it as a zombie
- the parent calls wait or waitpid