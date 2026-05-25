
**Starvation** happens when a thread _could_ run, but never gets scheduled or never acquires a resource because others keep “cutting in line.”

### Analogy

A single slow customer is always skipped because new VIP customers keep arriving.

### Example (priority-based scheduling)

- Thread A = low priority
- Threads B, C, D = high priority and keep arriving

CPU always picks high priority threads → A keeps waiting forever.

### Or lock example

- Lock is heavily contended
- Some threads repeatedly lose the race to acquire it
- They _never die_, but _never progress_