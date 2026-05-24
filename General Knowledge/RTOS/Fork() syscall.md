In Linux, a new process is created by means of the fork() - system call. The OS performs the following functions
1) allocate slot in process table for new process
2) assign a unique ID to this
3) duplicate the original known as the parent to the child
4) assign the child process to the ready to run state (processes have different states)
5) return the ID for the child to the parent and return 0 to the child ID

Note:
- fork actually is called once but returns twice
- in order to know all the pids, issue a `getpid()` call before and after forking

`getpid()` is a syscall that lets both processes discover their own identity.

the type is `pid_t`


#### Important Syscalls

- fork creates a child process with the data and code inherited from the parent
- exec() replaces the code and data and then executes the code
- exit() terminates the process. not