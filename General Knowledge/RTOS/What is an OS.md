
An OS is the interface between the user and the hardware

It does a lot of things:
1) controls and coordinates the user of hardware devices among all the apps and users
2) Provides standard services such as process, cpu scheduling, memory management, file system, networking
3) User mode and kernel mode
	1) user mode is where normal apps like browsers run, they have limited access so they cant modify critical memory.
	2) kernel mode is where the kernel (core OS code) runs with full access to the CPU, memory and devices to it can manage hardware
	3) CPU needs to switch between these modes so that user programs stay isolated and the system remains stable
4) OS implements a VM that is easier to program than bare hardware (e.g. system calls, files, processes are all higher level abstractions)
5) Kernel is the ‘one program’ running at all time on the computer

Why do we need an OS?
- gather the hardware 