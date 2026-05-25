processes communicate within a system
reasons for doing this:
- information sharing
- computation speedup
- modularity
- convenience

IPC can be done via message passing or shared memory

#### Passing:
- from client to server, or client to client
- small amounts of data
- simple

#### Shared Memory
- created and gain access to memory regions
- maximum speed and convenience of communication

Question: Distinguish between the client-server, known as C-S, and peer-to-peer, known as P-P, models of distributed systems

Answer: The C-S requests services that are provided by the S. while P-P is equal P can request and provide services – or both. A node may request a service from another P, or the node may in fact provide such a service to other peers in the system

**Client-Server:** A central server provides resources/services and clients request them, creating a clear distinction between provider and consumer (e.g., a web browser requesting a webpage from a web server).

**Peer-to-Peer (P2P):** Every node acts as both client and server simultaneously, communicating directly with each other without a central authority (e.g., BitTorrent file sharing).

---

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

FIFO

Message queues

