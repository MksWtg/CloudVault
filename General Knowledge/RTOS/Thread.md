A **thread** is the smallest unit of execution within a process that runs independently but shares the same memory space as other threads in that process. Threads within the same process share code, heap, and global variables, but each thread has its own stack and program counter. This makes threads lightweight compared to processes and useful for parallel tasks like handling multiple clients or performing background work.

```C
#include <stdio.h>
#include <pthread.h>

void* print_message(void* arg) {
    printf("Hello from thread!\n");
    return NULL;
}

int main() {
    pthread_t t;

    pthread_create(&t, NULL, print_message, NULL);
    pthread_join(t, NULL);

    printf("Back in main thread\n");
    return 0;
}
```

Threads dont need IPC since they share common data

they dont need their own address space sot hey are cheap to create

#### Threads vs Processes
