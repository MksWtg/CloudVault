See: [[critical section]]
unnamed semaphores are memory based:
sem_t sem;
destroyed using destroy

named semaphores are system wide:
sem_open("/mysem", O_CREAT, 0666, initial_value);

can be closed or unlinked (removed)


Consider:

“How can a semaphore be used by other processes than the one that created it?”

Maybe using a common name
# Answer part 1: Named semaphores

### Mechanism: **Filesystem name (IPC namespace)**

A named semaphore is created like this:

```c
sem_open("/mysem", O_CREAT, 0666, 1);
```

Answer 2:
```C
sem_init(&sem, 0, 1);
```
put it in shared memory- the adress pointed to by sem needs to be in shared memory

```C
#include <stdio.h>
#include <unistd.h>
#include <sys/mman.h>
#include <semaphore.h>

typedef struct {
    sem_t sem;
    int shared_data;
} shared_region;

int main() {

    shared_region *region = mmap(
        NULL,
        sizeof(shared_region),
        PROT_READ | PROT_WRITE,
        MAP_SHARED | MAP_ANONYMOUS,
        -1,
        0
    );

    // IMPORTANT: process-shared semaphore
    sem_init(&region->sem, 1, 1);

    region->shared_data = 0;

    for (int i = 0; i < 5; i++) {
        sem_wait(&region->sem);

        region->shared_data++;
        printf("Writer: %d\n", region->shared_data);

        sem_post(&region->sem);

        sleep(1);
    }

    return 0;
}
```