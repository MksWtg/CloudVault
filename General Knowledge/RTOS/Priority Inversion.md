> A low-priority thread holds a resource needed by a high-priority thread, but gets preempted by medium-priority threads.

### Classic scenario

Threads:

- L = low priority
- M = medium priority
- H = high priority

Shared lock = `L1`

### Step-by-step:

1. **L acquires lock L1**
2. **H becomes ready, tries to get L1 → blocked**
3. Now H is waiting on L (low priority)
4. But M (medium priority) keeps running
    - M preempts L
    - L never gets CPU time to release L1
5. H is effectively blocked by M, even though M is unrelated to the lock