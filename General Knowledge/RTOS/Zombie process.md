
A zombie process is a process that has finished execution but still remains in the process table.  
It exists because its parent process has not yet read its exit status using wait.  
Since it is already dead, it does not use CPU or memory resources.  
It stays as an entry until the parent acknowledges its termination.