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
- exit() terminates the process. note that void exit(int status) where status is used as the return value of the process. exit(i) can be used to announce success or failure e.g. exit(0) or exit(-1)
- wait() suspends the parent process until one of the child processes terminates.
	- when a process creates a child with fork the two run independently. sometimes the parent wants to pause, so thats what wait and waitpid do. wait pauses the parent until any one of the children finish. when child finishes, the kernel wakes the parent.
	- without wait, a child can become a zombie- it finishes executing but still has an entry in the process table because parent has not yet collected its execute status using wait()
#### Note:

`return 0;` and `exit(0);` both terminate a program successfully, but they work differently depending on where they are used.
```C
void f() {
    return;   // only leaves f()
}
```


```C
void f() {
    exit(0);  // kills whole program
}
```


#### More Info

to wait for a particular child to