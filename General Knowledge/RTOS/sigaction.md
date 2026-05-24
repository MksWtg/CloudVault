
`sigaction` is a POSIX system call used to **define how a process should respond to a signal**.

```C
#include <signal.h>

int sigaction(int signum,
              const struct sigaction *act,
              struct sigaction *oldact);
```