process: the program currently executing
burst time: how much time the process needs to execute, not necessarily all at once, it may execute in chunks
arrival time: the moment a process becomes ready to run (the scheduler cannot run it before arrival)
completion time: the time when the process fully finishes
turnaround time: total time spent in the system (turnaround = completion - arrival). turnaround includes waiting time, and pauses between round robin slices.