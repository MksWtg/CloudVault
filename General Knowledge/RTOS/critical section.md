Critical Section (region) — code that only one thread can execute at a time (e.g., code that modifies shared data) ➢Lock before entering a critical section ➢Unlock when leaving a critical section ➢A thread wants to enter a locked critical section must wait until it’s unlocked


Protect a critical section by first acquire() a lock then release() the lock ➢ Boolean variable indicating if lock is available or not

this is called a spinlock as the process spins in place while attempting to acquire it, like advanced installer

As usual synchronization primitive, a semaphore is based on a variable. This variable may be incremented or decremented, and its state will represent ability to acquire lock. • Synchronization tool that provides more sophisticated ways (than Mutex locks) for processes to synchronize their activities. • Semaphore S – integer variable and its values (+/-): 1. Positive semaphore = number of (additional) threads that can be allowed into the critical section 2. Negative semaphore = number of threads blocked 3. Binary semaphore has an initial value of 1 -- Same as a mutex lock 4. Counting semaphore has an initial value =>1

a semaphore keeps a queue of waiting processes
when an icnrement from -2 to -1 happens, it frees up a process

processes are put to sleep or woken up by moving them between queues like waiting queue

sem wait decrements
sem post or signal increments

busy waiting is using a loop
we dont do that, unix moves to wait queue


---

There is an idea to use disabling interrupts when reaching the critical section. unfortunately this is not a viable option as it breaks the whole OS, scheduling stops happenign and context switcing stops happening