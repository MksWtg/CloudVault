
A **message queue** is an IPC (Inter-Process Communication) mechanism where processes communicate by **sending and receiving discrete messages** stored in a kernel-managed queue.

They are different to pipes and FIFO:

| Feature           | Pipe        | Message Queue       |
| ----------------- | ----------- | ------------------- |
| Data type         | Byte stream | Structured messages |
| Boundaries        | No          | Yes                 |
| Selective reading | No          | Yes (by type)       |
| Kernel storage    | Buffer      | Queue of messages   |

The POSIX api includes:
- mq_open
- mq_send
- mq_recieve
- mq_close
- mq_unlink

```C
#include <stdio.h>
#include <fcntl.h>
#include <sys/stat.h>
#include <mqueue.h>
#include <string.h>

int main() {
    mqd_t mq;
    const char *queue_name = "/myqueue";

    struct mq_attr attr;
    attr.mq_flags = 0;
    attr.mq_maxmsg = 10;
    attr.mq_msgsize = 100;
    attr.mq_curmsgs = 0;

    mq = mq_open(queue_name, O_CREAT | O_WRONLY, 0644, &attr);

    char msg[] = "Hello from sender";

    mq_send(mq, msg, strlen(msg) + 1, 0);

    printf("Message sent\n");

    mq_close(mq);
    return 0;
}
```


#### Close vs unlink?

They do completely different things, even though they often appear together in IPC (pipes, FIFOs, message queues, files).

`close(fd)` tells the OS:

> “I’m done using this open file/pipe/socket descriptor.”


- Removes the **process’s reference** to the open file description
- Decrements internal reference count
- May allow kernel resources to be freed (if no one else is using it)

`unlink("file")` tells the OS:

> “Remove this filename from the directory.”

Deletes the **directory entry (name → inode mapping)**


#### Improvement over FIFO:
- fifo does not have mesage boundaries- HELLO WORLD is just HELLOWORLD but mq does
- mq can have priority
- FIFO cannot choose categories or types it just reads sequentially

