
See: Thread

```C
#include <stdio.h>
#include <pthread.h>

#define NUM_THREADS 5

// Thread function
void* worker(void* arg) {
    int id = *(int*)arg;

    printf("Thread %d is running\n", id);

    return NULL;
}

int main() {
    pthread_t threads[NUM_THREADS];
    int ids[NUM_THREADS];

    // Create threads
    for (int i = 0; i < NUM_THREADS; i++) {
        ids[i] = i;

        pthread_create(&threads[i],
                       NULL,
                       worker,
                       &ids[i]);
    }

    // Join threads (wait for completion)
    for (int i = 0; i < NUM_THREADS; i++) {
        pthread_join(threads[i], NULL);
    }

    printf("All threads finished\n");

    return 0;
}
```