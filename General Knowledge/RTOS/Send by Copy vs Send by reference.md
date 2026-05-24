
#### Send by Copy

A **duplicate** of the data is sent to the receiver — original remains unchanged.

|✅ Pros|❌ Cons|
|---|---|
|Safer — sender and receiver are fully independent|Overhead of copying large data is expensive|
|No risk of receiver corrupting sender's data|Uses more memory (two copies exist)|

#### Send by Reference

A **pointer/reference** to the data is sent — both share the same memory.

|✅ Pros|❌ Cons|
|---|---|
|Fast and memory efficient — no copying needed|Receiver can accidentally modify sender's data|
|Good for large data structures|Requires careful synchronization to avoid race conditions|