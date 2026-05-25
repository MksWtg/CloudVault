
`sigsuspend()` is a POSIX system call used to **temporarily replace a process’s signal mask and suspend execution until a signal arrives**.

A signal mask is a sigset_t

you replace the existing sigset mask with a new one and wait for a signal to arrive and then discard teh mask and go back to the old one

