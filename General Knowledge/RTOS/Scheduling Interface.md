API that allows a dev to interact with the scheduler

sched_setscheduler(pid_t pid, int policy, struct schedparam* schedparameters)

sets scheduling policy
can also get scheduling policy
sched_yield(void) causes the calling thread to relinquish the CPU
sched_get_priority_max (int policy)
 and the min equivalent let you see what the highest priority you can assign is