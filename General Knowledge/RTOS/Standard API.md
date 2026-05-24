A standard API (Application Programming Interface) is a defined set of functions and rules that let programs request services from the operating system in a consistent way.

For example, `read()` is part of the POSIX standard API for Unix-like systems. It provides a standard way for programs to read data from a file or device without needing to know how the hardware or filesystem works internally.

In practice, `read()` is usually a C library wrapper (in something like glibc) that eventually makes a system call into the kernel. So the API is the programmer-facing function, while the operating system implements the actual low-level work behind it.

![[Pasted image 20260524213019.png]]
