
`sigprocmask` is a POSIX system call used in Unix-like operating systems to **examine or change the set of signals blocked for a process or thread**.

In C it translates to a direct function:

```C
#include <signal.h>

int sigprocmask(int how,
                const sigset_t *set,
                sigset_t *oldset);
```

How says how to handle the signal- you can add it to the blocked set, to the unblocked set and to replace the mask

Set is a pointer to the set of signals to modify

If oldset is not null it uses the previous mask

E.g. we can block Ctrl C temporarily:

```c
#include <stdio.h>
#include <signal.h>
#include <unistd.h>

int main() {
    sigset_t set;

    sigemptyset(&set);
    sigaddset(&set, SIGINT);

    // Block SIGINT
    sigprocmask(SIG_BLOCK, &set, NULL);

    printf("SIGINT blocked for 10 seconds\n");
    sleep(10);

    // Unblock SIGINT
    sigprocmask(SIG_UNBLOCK, &set, NULL);

    printf("SIGINT unblocked\n");

    while (1);
}
```

E.g. we dont want to interrupt during critical sections

Mask is a bitmask e.g. 000 means allow all three signals and 111 means block them all, each bit corresponds to a signal

SIGKILL SIGSTOP and SIGTRACE cannot be overriden