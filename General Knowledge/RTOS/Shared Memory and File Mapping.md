**Shared memory** and **file mapping** are two OS mechanisms for letting multiple processes access the _same data in memory_, instead of copying it back and forth.


Share memory:
Shared memory = a region of RAM mapped into multiple processes’ address spaces.

A **file mapping** is when the OS maps a file directly into memory.

shared memory is very fast
flexible

```C
#include <stdio.h>
#include <fcntl.h>
#include <sys/mman.h>
#include <sys/stat.h>
#include <unistd.h>

int main() {
    const char *name = "/my_shm";

    // create shared memory object
    int fd = shm_open(name, O_CREAT | O_RDWR, 0666);

    // set size
    ftruncate(fd, sizeof(int));

    // map it into memory
    int *ptr = mmap(NULL, sizeof(int),
                    PROT_READ | PROT_WRITE,
                    MAP_SHARED,
                    fd, 0);

    // write into shared memory
    *ptr = 42;
    printf("Writer wrote: %d\n", *ptr);

    sleep(10); // keep alive so reader can access it

    return 0;
}
```