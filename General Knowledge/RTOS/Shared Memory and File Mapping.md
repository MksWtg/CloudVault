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

`shm_open()` — “create or open shared memory object”

- It does **NOT give you memory**
- It gives you a **file descriptor (fd)**

# `mmap()` — “map memory into your process”

## What it does

`mmap()` takes:

- a file descriptor (or shared memory object)
- and maps it into your process’s virtual address space
---

in shared memory you control the layout so it is flexible
but prone to race conditions

```C
#include <stdio.h>
#include <fcntl.h>
#include <sys/mman.h>
#include <sys/stat.h>
#include <unistd.h>

int main() {
    const char *name = "/my_shm";

// this just gives a file descriptor
    int fd = shm_open(name, O_CREAT | O_RDWR, 0666);
    // needed
    ftruncate(fd, sizeof(int));

// this is the shape of the shraed data
    int *ptr = mmap(NULL, sizeof(int),
                    PROT_READ | PROT_WRITE,
                    MAP_SHARED,
                    fd, 0);

// dereference and set value
    *ptr = 42;
    printf("Writer wrote: %d\n", *ptr);

    sleep(10); // keep alive so reader can access

// delete
    shm_unlink(name);
    return 0;
}
```