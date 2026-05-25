See: [[critical section]]
unnamed semaphores are memory based:
sem_t sem;
destroyed using destroy

named semaphores are system wide:
sem_open("/mysem", O_CREAT, 0666, initial_value);

can be closed or unlinked (removed)