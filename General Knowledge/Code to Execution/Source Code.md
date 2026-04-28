Source code are human readable instructions written in text files. These instructions describe how a software works. 

There exist programs that take source code as input and then perform a series of operations finally "executing" these instructions on the machine.

E.g. of source code: a file `main.c`

The contents of which are:

```c
#include <stdio.h>

int main() {
	int age;
	printf("Please enter your age:\n");
	scanf("%d", age");
	printf("Your age is: %d\n", age);
	return 0;
}
```

These instructions are called source code. They were written by humans for another humans. The syntax used to write the code is known as the language. Usually the extension of the source code indicates the language- in this case, `.c` after the file name.