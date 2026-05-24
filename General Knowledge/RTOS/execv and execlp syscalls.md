Both are system calls in Unix-like systems used to replace the current process with a new program.  
execv takes the program path and an array of arguments (argv-style).  
execlp takes the program name and a variable list of arguments, and it searches PATH to find the executable.  
Neither returns on success because the current process is completely replaced.

