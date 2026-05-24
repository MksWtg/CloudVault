
System call is how a program does special things that require elevated permissions.

the kernel executes these

open opens a file and returns a file descriptor for reading or writing;
read reads data from a file descriptor into memory; write writes data from memory to a file descriptor; close closes an open file descriptor; fork creates a new process by duplicating the current one; execve replaces the current process with a new program; wait waits for a child process to finish and collects its exit status; mmap maps files or devices into memory for direct access; brk changes the size of the process’s data segment for memory allocation; exit terminates the current process and returns a status code to the OS