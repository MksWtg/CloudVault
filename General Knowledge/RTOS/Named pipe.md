
See: [[Pipes]]

you create a named pipe with mkfifo (not with pipe in c)

```C
mkfifo("mypipe", 0666);
```

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