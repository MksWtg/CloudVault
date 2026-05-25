
A **deadlock** happens when a set of threads are each waiting for resources held by others in the set, forming a cycle. None can proceed.

### Simple analogy

Two people, two forks:

- Thread A holds Lock 1, waits for Lock 2
- Thread B holds Lock 2, waits for Lock 1

Neither will ever release what they have → both wait forever.

Example


Thread A:
  lock(L1)
  lock(L2)

Thread B:
  lock(L2)
  lock(L1)

---


Four coffman conditions:
1) circular wait- a cycle exists where each is waiting for the next
2) no preemption- resources cannot be forcefully taken
3) hold and wait- a process is holding and waiting
4) mutual exclusion- a non shareable resource exists