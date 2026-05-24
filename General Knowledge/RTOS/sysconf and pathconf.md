These are two c library functions that wrap sys calls

#### `sysconf`

Returns **system-wide configuration limits** at runtime — values not tied to any specific file or directory.

Examples: max number of processes, number of CPUs, page size, max open files system-wide.


```c
long val = sysconf(_SC_NPROCESSORS_ONLN); // number of online CPUs
long val = sysconf(_SC_PAGESIZE);          // memory page size
```

#### `pathconf`

Returns **file/directory-specific configuration limits** — values that can vary depending on the filesystem or path.

Examples: max filename length, max path length, max symlinks for a specific path.


```c
long val = pathconf("/home", _PC_NAME_MAX);  // max filename length at /home
long val = pathconf("/tmp", _PC_PATH_MAX);   // max path length at /tmp
```

execl(), execlp(), execle()        ← C library wrappers
execv(), execvp(), execvpe()       ← C library wrappers
        ↓
    execve()                       ← the actual syscall