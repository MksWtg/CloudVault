
Pipes: 
- they are in the posix api
- they are synchronous
- the kernel safeguards data that travels through pipes
- a parent writes to a pipe that a child then reads

the unix pipe syscall (or c pipe function) populates fd with 2 file descriptors, you write to the write one and read from the read one

```c
#include <stdio.h>
#include <unistd.h>

int main() {
    int fd[2];
    pipe(fd);

    write(fd[1], "hello", 5);

    char buf[10];
    read(fd[0], buf, 5);

    buf[5] = '\0';

    printf("%s\n", buf);
}
```


they are synchronized by the operating system kernel

what is synchronization?
kernel coordinates access so multiple processes dont corrupt it


e.g. if a process tries to read but nothing has written yet, the kernel suspends the process- it is blocked

> you can override blocking on read with O_NONBLOCK

> if you try to read from a file but the writing end has been closed, it returns 0 


if the writer writes too much the writer blocks

(even though pipe is used in one process, after fork multiple processes may inherit the same file descriptor)

ready from fd[0] write to fd[1]

0 1 2 are usually reserved fds for stdin stdout and stderr