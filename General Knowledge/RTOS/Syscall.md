
System call is how a program does special things that require elevated permissions.

the kernel executes these

open opens a file and returns a file descriptor for reading or writing;
read reads data from a file descriptor into memory;
write writes data from memory to a file descriptor;
close closes an open file descriptor;
fork creates a new process by duplicating the current one;
execve replaces the current process with a new program;
wait waits for a child process to finish and collects its exit status;
mmap maps files or devices into memory for direct access;
brk changes the size of the process’s data segment for memory allocation;
exit terminates the current process and returns a status code to the OS

how does syscall pass params?
1) pass via the stack by pushing
2) can put into registers (doesnt work if many params)
3) can put into memory (address passed as a param in a register)

A system call executes kernel code

A system call can cause a process to **suspend (block)** if the requested resource is not immediately available. Instead of continuing execution, the operating system puts the process into a waiting state until the resource becomes available, and only then resumes it.

A syscall might return a value which represents if it succeeded or not.

The system call interface interpreters (intercepts) function calls in the API and invokes the necessary system calls within the operating system

Typically, a number associated with each system call. System-call interface maintains a table indexed according to these numbers

Caller doesnt need to know how the sys call is implemented, just to obey the API and understand what OS will do

Details of the OS hidden by API

Disadvantae with using the same interface for S/