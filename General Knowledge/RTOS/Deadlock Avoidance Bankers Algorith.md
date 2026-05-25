See: [[Deadlock]]


Bankers algo says that before the resource is granted the system should be safe in that state if it were to be granted

n processes 
m resource types

Available[m_i] is the number of each kind of resource available

`Max [n_i] [m_i]` is the maximum demand of process `n_i` for resource `m_i`

Allocation `[n_i]` `[m_i`] is which resource which process is holding

need = max - allocation, how many left


advantages: no need to preempt and then rollback
it tries to allow progress


disadvantages:
maximum resource consumption has t be known
processes need to be independent and not synchronize otherwise
there must be a fixed numner, cant add or remove reosurces
huge overhead to run the algo