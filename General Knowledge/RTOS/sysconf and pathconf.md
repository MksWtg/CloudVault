These are two c library functions that wrap sys calls

#### `sysconf`

Returns **system-wide configuration limits** at runtime — values not tied to any specific file or directory.

Examples: max number of processes, number of CPUs, page size, max open files system-wide.

c

```c
long val = sysconf(_SC_NPROCESSORS_ONLN); // number of online CPUs
long val = sysconf(_SC_PAGESIZE);          // memory page size
```

