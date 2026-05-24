
#### Synchronous Communication

Sender **blocks and waits** for the receiver to respond before continuing.

|✅ Pros|❌ Cons|
|---|---|
|Simple to understand and implement|Sender is blocked — wastes CPU time waiting|
|Response is immediate and guaranteed|Poor performance if receiver is slow|
|Easy error handling (errors caught right away)|Can cause deadlock if both sides wait on each other|

---

#### Asynchronous Communication

Sender **sends and continues** without waiting for a response.

|✅ Pros|❌ Cons|
|---|---|
|Sender isn't blocked — better performance|More complex to implement and debug|
|Better scalability for many concurrent processes|Response arrives later — harder error handling|
|No risk of deadlock from waiting|Requires buffers/queues to store messages|
