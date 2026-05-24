
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

Caller doesn't need to know how the sys call is implemented, just to obey the API and understand what OS will do

Details of the OS hidden by API

Disadvantage with using the same interface for S/W and H/W is you cant capture functionality of different devices using the same API

#### What are the advantages and disadvantages of using the same system call interface for manipulating both files and devices?

Advantages:
- simple programming model with functions like open, read, write, close
- Easier OS design and extensibility since all devices are handled throuhg a file like interface, so if we want a new device driver we implement the standard file operations for the driver like read write and open without changing the rest of the OS
- and it is a uniform abstraction, user programs dont need to know if it is a disk file or a hardware device

Disadvantages:
- not all devices behave like files- files are sequential or random access and are finite data stored on disk. devices may be interactive, they might stream, etc. so the file api is bad for device features
- some device features dont fit read/write like changing the screen resolution etc.
- forcing everything into a file abstraction adds overh