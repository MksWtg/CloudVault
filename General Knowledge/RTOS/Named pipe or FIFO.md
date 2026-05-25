
See: [[Pipes]]

these showed up in POSIX 4

you create a named pipe with mkfifo (not with pipe in c)

```C
mkfifo("mypipe", 0666);
```

> 0666 means user group and others can read and write but not execute 

The data in a named pipe is not stored in disk, it is in buffers managed by kernel
kernel also handles synchronization and blocking

Comparison vs regular pipe

| Feature                  | Unnamed Pipe                                       | Named Pipe (FIFO)    |
| ------------------------ | -------------------------------------------------- | -------------------- |
| Created with             | `pipe()`                                           | `mkfifo()`           |
| Has filename             | No                                                 | Yes                  |
| Visible in filesystem    | No (does not show up in ls but the other one does) | Yes                  |
| Related processes needed | Usually yes                                        | No                   |
| Lifetime                 | Until processes close it                           | Exists until deleted |
| Parent-child IPC         | Excellent                                          | Possible             |
| Unrelated process IPC    | Hard                                               | Easy                 |
| Kernel buffering         | Yes                                                | Yes                  |
| Blocking behavior        | Yes                                                | Yes                  |
named pipes exist beyond the process that created them, they have to be actively deleted (i think pipes are cleaned up by the kernel)

unlink must be called to clean up named pipes

named pipes are usually half duplex- data flows one way

writing to FIFO:

```c
#include <stdio.h>
#include <fcntl.h>
#include <unistd.h>
#include <string.h>

int main() {
    int fd;
    char *msg = "Hello from writer process";

    fd = open("myfifo", O_WRONLY);

    write(fd, msg, strlen(msg) + 1);

    printf("Message sent\n");

    close(fd);
    return 0;
}
```

```C
#include <stdio.h>
#include <fcntl.h>
#include <unistd.h>

int main() {
    int fd;
    char buffer[100];

    fd = open("myfifo", O_RDONLY);

    read(fd, buffer, sizeof(buffer));

    printf("Received: %s\n", buffer);

    close(fd);
    return 0;
}
```