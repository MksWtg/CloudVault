Both are system calls in Unix-like systems used to replace the current process with a new program.  
execv takes the program path and an array of arguments (argv-style).  
execlp takes the program name and a variable list of arguments, and it searches PATH to find the executable.  
Neither returns on success because the current process is completely replaced.

Example:

```C
#include <stdio.h>
#include <unistd.h>

int main() {
    char *args[] = {
        "ls",     // argv[0] is conventionally program name
        "-l",
        "/tmp",
        NULL
    };

    printf("Before execv\n");

    execv("/bin/ls", args);

    // Only runs if execv fails
    perror("execv failed");
    return 1;
}
```

```C
#include <stdio.h>
#include <unistd.h>

int main() {
    printf("Before execlp\n");

    execlp("ls",      // searched in PATH
           "ls",      // argv[0]
           "-l",
           "/tmp",
           (char *)NULL);

    // Only runs if execlp fails
    perror("execlp failed");
    return 1;
}
```