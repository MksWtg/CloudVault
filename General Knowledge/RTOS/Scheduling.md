Scheduling is the operating system’s process of deciding which running task or thread gets to use the CPU at any given time. It manages the order and time each process runs so that multiple programs can share the CPU efficiently and fairly.

---

## Criteria

Scheduling Criteria 
. CPU utilization – Percentage of time the CPU is not idle 2

Throughput – # of processes that complete their execution per time unit or completed processes per time unit 

Turnaround time – amount of time to execute a particular process 

Waiting time – amount of time a process has been waiting in the ready queue 

Response time – amount of time it takes from when a request was submitted until the first response is produced, not output (for timesharing environment) or response latency 

Predictability -- Variance in any of these measures 

Scheduling Algorithm Optimization Criteria – Max CPU utilization – Max throughput – Min turnaround time – Min waiting time – Min response time

---

## Algos:

- first come first serve depends on the order of arrival
	- can be good if short ones come first
	- bad if long ones come first (called the convoy effect)
- shortest job first makes the shortest job come first
- shortest remaining time first -> preempts, so if a shorter process comes it pushes it up
- Priority scheduling pushes some up by priority
- RR we know
	- time slice might take 10ms to 100ms 
	- context swtichign takes 0.1 to 1 ms
---

A **Multilevel Feedback Queue (MLFQ)** is a CPU scheduling algorithm where processes are placed in **multiple priority queues**, and they can **move between queues based on their behavior over time**.

Unlike fixed priority systems, MLFQ _learns from how a process behaves_.

E.g. 2RR and one FCFS